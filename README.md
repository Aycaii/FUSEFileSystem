# FUSE File System

A Linux file system implemented using FUSE.

To mount: `make mount`

Root of the file system will be at `mnt/`

To unmount: `make unmount`



File System Layout:

  - 1MB = 256 pages (4k blocks)
  - page 0 = 256 inodes (each 8 bytes)
  - page 1 & inode 1 = root directory
  - the root directory is just an array of 128 char[16]'s
    - max filename length = 15
    - ent[0] == '\0' means unused
