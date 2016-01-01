---
redirect_from:
  /blog/2008/12/just-found-out-that-in-order-to-make.html
---
Just found out that in order to make a Kingston DataTraveler USB drive bootable, it needs to be formatted as a FAT32 disk. It comes originally formatted as a FAT16 disk, and syslinux would not work correctly on it. You can format it from the Windows command prompt by typing "format /fs:fat32 F:" (replace the F with the correct drive letter).
