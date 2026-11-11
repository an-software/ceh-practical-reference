# Forensics

Keywords: evidence integrity SHA256 memory [Volatility](../tools/volatility.md) packets pcap timeline strings.

Preserve an original and analyze a working copy. Record source, collection time/timezone, hash and actions. Live acquisition can alter a system; document the method.

```bash
sha256sum memory.raw
file sample.bin
strings -a -n 8 sample.bin | head -n 40
# From an installed Volatility 3 environment:
python3 vol.py -f memory.raw windows.info
python3 vol.py -f memory.raw windows.pslist
python3 vol.py -f memory.raw windows.netscan
tshark -r lab.pcapng -q -z conv,tcp
```

Tools in this example: [file](../tools/file.md), [sha256sum](../tools/sha256sum.md), [strings](../tools/strings.md), [tshark](../tools/tshark.md).

Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\memory.raw
```

Tools in this example: [Get-FileHash](../tools/get-filehash.md).

Correlate processes, network connections and timestamps. Strings are leads, not proof of execution. Store images and captures outside source history.

Troubleshooting: confirm image type and OS before choosing plugins. Missing symbols may need downloads and a writable cache; prepare these for offline work. Truncated images and capture loss limit conclusions. Normalize timezones before joining timelines.

Sources: [Volatility 3](https://github.com/volatilityfoundation/volatility3), [tshark manual](https://www.wireshark.org/docs/man-pages/tshark.html).

## Packet analysis: credentials, flags, DNS and suspected floods

```bash
tshark -r lab.pcapng -Y 'http.request.method == "POST"'
tshark -r lab.pcapng -Y 'tcp.flags.syn == 1 && tcp.flags.ack == 0' \
  -T fields -e ip.src -e ip.dst -e tcp.dstport
tshark -r lab.pcapng -Y 'dns.flags.response == 0' \
  -T fields -e dns.qry.name | sort -u
tshark -r lab.pcapng -q -z endpoints,ip -z conv,tcp
```

Tools in this example: [tshark](../tools/tshark.md).

[Wireshark](../tools/wireshark.md) display filters include `smtp`, `pop`, [`ftp`](../tools/ftp.md), `dns`, `ip.addr == 192.0.2.10` and `tcp.port == 443`. Use Follow TCP Stream and Find Packet (packet bytes, string) to inspect a lab conversation. TLS protects application content unless appropriate session secrets/decryption material are available. POST alone does not imply exposed passwords.

For a question about “bit 3,” inspect the named protocol and field; bit numbering conventions differ. Prefer named filters such as `tcp.flags.push` rather than guessing a numeric bit. Many SYNs alone do not establish DoS: compare rates over time, completed handshakes, source distribution and capture-loss indicators. Source IPs can be spoofed. For DNS tunneling/covert TCP examples, inspect name length, repeated domains, timing and anomalous header values before attempting any decoding; preserve ordering and the untouched capture.

## Steganography and hidden data

```bash
file lab-image.jpg
exiftool lab-image.jpg
steghide info lab-image.jpg
steghide extract -sf lab-image.jpg -xf evidence/extracted.txt
# PNG/BMP bit-plane analysis, not a JPEG tool:
zsteg lab-image.png
binwalk lab-image.png
```

Tools in this example: [binwalk](../tools/binwalk.md), [ExifTool](../tools/exiftool.md), [file](../tools/file.md), [Steghide](../tools/steghide.md), [zsteg](../tools/zsteg.md).

Use a working copy. [Steghide](../tools/steghide.md) prompts for the lab passphrase. [OpenStego](../tools/openstego.md) has a separate Extract Data workflow: choose the stego file, output directory and supplied password. Whitespace steganography can use [`snow -C -p "LAB_PASSWORD" lab-text.txt`](../tools/snow.md) to extract/decompress; program names differ across platforms. Do not normalize whitespace first. [Stegseek](../tools/stegseek.md) is useful only for supported [steghide](../tools/steghide.md) data; not every image contains hidden data or uses that format.

## Static malware and executable triage

```bash
sha256sum lab-sample.bin
file lab-sample.bin
strings -a -n 8 lab-sample.bin | head -n 50
readelf -h lab-sample.elf
objdump -f lab-sample.exe
```

Tools in this example: [file](../tools/file.md), [objdump](../tools/objdump.md), [readelf](../tools/readelf.md), [sha256sum](../tools/sha256sum.md), [strings](../tools/strings.md).

Inspect PE/ELF headers and the entry-point field in [PEview](../tools/peview.md), [Ghidra](../tools/ghidra.md), [radare2](../tools/radare2.md) or an appropriate binary viewer. Strings and antivirus signatures do not reliably locate an entry point. High entropy may indicate packing, compression or encryption; it does not prove malware. Compare entropy over equivalent file ranges and hash the actual file identified by the task.

[FTK Imager](../tools/ftk-imager.md), [Autopsy](../tools/autopsy.md)/[The Sleuth Kit](../tools/sleuth-kit.md) and [Volatility](../tools/volatility.md) address different evidence types. [YARA](../tools/yara.md) classifies patterns; [ProcMon](../tools/procmon.md) records behavior; [Regshot](../tools/regshot.md) compares registry snapshots. [PEStudio](../tools/pestudio.md)/[PEiD](../tools/peid.md), [Dependency Walker](../tools/dependency-walker.md) and [Redline](../tools/redline.md) appear in the supplied historical tool list; check compatibility before relying on them. Dynamic analysis with [GDB](../tools/gdb.md)/[IDA](../tools/ida.md)/[WinDbg](../tools/windbg.md) or a dedicated analysis service belongs in an isolated disposable environment. Do not execute an unknown sample on this PC or upload confidential artifacts to public analysis services.
