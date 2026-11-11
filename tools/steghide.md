# Steghide

Priority writeup tool. Purpose: hide/extract data in supported cover formats, including certain JPEG/audio files.

## Basic workflow

1. Preserve the original and identify the actual file type.
2. Inspect the candidate using Steghide and the lab-supplied passphrase.
3. Extract to a separate evidence path; inspect and hash the result.

## Example

```bash
mkdir -p evidence
file lab-image.jpg
steghide info lab-image.jpg
steghide extract -sf lab-image.jpg -xf evidence/extracted.txt
```

Tools in this example: [file](file.md).

## Troubleshooting

A failed extraction may indicate an incorrect passphrase, unsupported cover format, corruption or no Steghide data. Not every image uses this format. Do not rewrite/recompress the original before analysis.

Related: [hidden-data workflow](../topics/forensics.md), [Stegseek](stegseek.md). References: [upstream documentation](https://steghide.sourceforge.net/documentation.php) (retrieval failed during this review), [Kali package-maintainer documentation and CLI help](https://www.kali.org/tools/steghide/) (checked as a fallback).
