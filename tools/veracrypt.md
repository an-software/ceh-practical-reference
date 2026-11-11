# VeraCrypt

Priority writeup tool. Purpose: encrypted volume/container access with the correct credentials.

## Basic workflow

1. Hash the original lab container and work from a copy.
2. Select an unused drive/mount point and the **existing** container file.
3. Use read-only mount options where practical; enter the supplied password, PIM/keyfiles if required.
4. Inspect the required lab file, record evidence and dismount afterward.

## Example

GUI: Select File → select the copied container → choose free drive → Mount → provide lab credentials. Use Mount Options for read-only access when supported. Do not choose Create Volume or format over an evidence container.

## Troubleshooting

Wrong PIM/keyfiles, damaged data or selecting the wrong container can resemble a password error. Mounting is not password recovery. A successful mount does not identify every file's original author or integrity.

Related: [cryptography](../topics/cryptography.md). Source: [VeraCrypt documentation](https://veracrypt.io/en/Documentation.html).
