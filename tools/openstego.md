# OpenStego

Priority writeup tool. Purpose: image-based data hiding/extraction and a separate watermarking workflow.

## Basic workflow

1. Preserve and hash the supplied image; work from a copy.
2. Select **Data Hiding → Extract Data**, not watermark verification.
3. Choose the stego image and a separate output folder; supply the lab password if required.
4. Extract, inspect the output type and record its hash/content as needed.

## Example

For a lab image, extract into ignored `evidence/openstego/`. If extraction fails, verify the image was created with a compatible OpenStego method before changing tools or passwords.

## Troubleshooting

Data hiding and watermarking are different modes. A file extension is not proof of a compatible steganographic container. Resizing or recompressing an image may destroy hidden data. OpenStego is not a generic decoder for all encrypted images.

Related: [forensics](../topics/forensics.md), [SNOW](snow.md). Source: [OpenStego](https://www.openstego.com/).
