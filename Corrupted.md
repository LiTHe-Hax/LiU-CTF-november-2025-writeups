# Corrupted writeup

## Solution

Use fls and icat to inspect sd img and extract deleted image.
deleted image is corrupt, inspect with `hexdump -C test.png | head`

Then look up png format and realize the the first 4 png signature bytes are missing. https://en.wikipedia.org/wiki/PNG

Append first 4 missing bytes:
`printf '\x89\x50\x4E\x47' | cat - broken_image.png > fixed_image.png`

Open image and find flag written in the image

## Recreate challenge files

These commands can be used to recreate the sd image file.

```bash
# Create fat16 image file
dd if=/dev/zero of=sd.img bs=1M count=10
mkfs.fat -F 16 sd.img

# Create photos directory
mmd -i sd.img ::/photos

# Remove first 4 bytes of png image header
dd if=whole_image.png of=broken_image.png bs=1 skip=4

# Copy and delete broken image on sd image file
mcopy -i sd.img broken_image.png ::/photos/broken_image.png
mdel -i fat16.img ::/photos/broken_image.png
```
