# Writing ISO Images to USB on Linux

1. Plug in USB

2. List drives - `sudo fdisk -l`

3. Unmount the usb - `umount /dev/sdb*`

4. Format the drive - `sudo mkfs.vfat /dev/sdb -I`

5. Use DD command to write the ISO image to the specified drive:
`dd if=~/Downloads/NameOfIsoImage.iso of=/dev/sdb`
, where `if` stands for input file and `of` stands for output file
Optionally may add `bs=1M` to specify byte writing speed to one million or `status=progress` to display progress. Be patient as it may take a while for the image to show up on your computer.

6. Alternative way to monitor dd progress - `pgrep -l 'dd$'`

## References
[Ostechnix - How to Create Bootable USB Drive Using DD Command](https://ostechnix.com/how-to-create-bootable-usb-drive-using-dd-command/)

## Tags
#linux
