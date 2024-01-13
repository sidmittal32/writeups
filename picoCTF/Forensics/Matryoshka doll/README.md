# Matryoshka doll

## Description
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)

## Approach
```
sidmittal32@sidmittal32-VirtualBox:~/Downloads$ binwalk dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg
651613        0x9F15D         End of Zip archive, footer length: 22
```

> Binwalk is a tool for searching a given binary image for embedded files and executable code. Specifically, it is designed for identifying files and code embedded inside of firmware images.

```
sidmittal32@sidmittal32-VirtualBox:~/Downloads$ binwalk -e dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg
651613        0x9F15D         End of Zip archive, footer length: 22

sidmittal32@sidmittal32-VirtualBox:~/Downloads$ ls -l
total 1504
-rw-rw-r-- 1 sidmittal32 sidmittal32 878136 Jan 11 16:21 cat.jpg
-rw-rw-r-- 1 sidmittal32 sidmittal32 651635 Jan 13 20:09 dolls.jpg
drwxrwxr-x 3 sidmittal32 sidmittal32   4096 Jan 13 20:34 _dolls.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads$ cd _dolls*
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted$ ls -l
total 376
-rw-rw-r-- 1 sidmittal32 sidmittal32 379143 Jan 13 20:34 4286C.zip
drwxrwxr-x 2 sidmittal32 sidmittal32   4096 Jan 13 20:34 base_images
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted$ cd base_images
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images$ ls -l
total 376
-rw-r--r-- 1 sidmittal32 sidmittal32 383936 Mar 16  2021 2_c.jpg
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images$ binwalk -e 2_c.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196041, uncompressed size: 201443, name: base_images/3_c.jpg
383803        0x5DB3B         End of Zip archive, footer length: 22
383914        0x5DBAA         End of Zip archive, footer length: 22

sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images$ ls -l
total 380
-rw-r--r-- 1 sidmittal32 sidmittal32 383936 Mar 16  2021 2_c.jpg
drwxrwxr-x 3 sidmittal32 sidmittal32   4096 Jan 13 20:34 _2_c.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images$ cd _2_c*
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ ls -l
total 196
-rw-rw-r-- 1 sidmittal32 sidmittal32 196229 Jan 13 20:34 2DD3B.zip
drwxrwxr-x 2 sidmittal32 sidmittal32   4096 Jan 13 20:34 base_images
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted$ cd base*
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls -l
total 200
-rw-r--r-- 1 sidmittal32 sidmittal32 201443 Mar 16  2021 3_c.jpg
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ binwalk -e 3_c*

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77649, uncompressed size: 79806, name: base_images/4_c.jpg
201421        0x312CD         End of Zip archive, footer length: 22

sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ ls -l
total 204
-rw-r--r-- 1 sidmittal32 sidmittal32 201443 Mar 16  2021 3_c.jpg
drwxrwxr-x 3 sidmittal32 sidmittal32   4096 Jan 13 20:35 _3_c.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images$ cd _3_c.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted$ ls -l
total 84
-rw-rw-r-- 1 sidmittal32 sidmittal32 77837 Jan 13 20:35 1E2D6.zip
drwxrwxr-x 2 sidmittal32 sidmittal32  4096 Jan 13 20:35 base_images
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted$ cd base*
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ ls -l
total 80
-rw-r--r-- 1 sidmittal32 sidmittal32 79806 Mar 16  2021 4_c.jpg
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ binwalk -e 4_c*

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ ls -l
total 84
-rw-r--r-- 1 sidmittal32 sidmittal32 79806 Mar 16  2021 4_c.jpg
drwxrwxr-x 2 sidmittal32 sidmittal32  4096 Jan 13 20:36 _4_c.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images$ cd _4_c.jpg.extracted
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ ls -l
total 8
-rw-rw-r-- 1 sidmittal32 sidmittal32 228 Jan 13 20:36 136DA.zip
-rw-r--r-- 1 sidmittal32 sidmittal32  81 Mar 16  2021 flag.txt
sidmittal32@sidmittal32-VirtualBox:~/Downloads/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted$ cat flag.txt
picoCTF{ac0072c423ee13bfc0b166af72e25b61}
```

## Flag
picoCTF{ac0072c423ee13bfc0b166af72e25b61}
