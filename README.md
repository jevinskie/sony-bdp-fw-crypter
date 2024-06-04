# sony-bdp-fw-crypter

Decrypt/encrypt Sony BDP (Blu-ray Player) firmware images.

It is really just a stupid 256 byte substitution table. Really.

Many thanks to [@niedbalski's](https://github.com/niedbalski) [python-bdpcrypt](https://github.com/niedbalski/python-bdpcrypt) repo for the substitution table!

# Example
```
$ binwalk msb15-fw-mb-dec.bin

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
67496         0x107A8         Mediatek bootloader
115848        0x1C488         Mediatek bootloader
346941        0x54B3D         Certificate in DER format (x509 v3), header length: 4, sequence length: 1284
347057        0x54BB1         Certificate in DER format (x509 v3), header length: 4, sequence length: 1288
356552        0x570C8         CRC32 polynomial table, little endian
361024        0x58240         CRC32 polynomial table, little endian
440880        0x6BA30         uImage header, header size: 64 bytes, header CRC: 0x6486887, created: 2018-09-20 00:03:37, image size: 2285568 bytes, Data Address: 0xDA00000, Entry Point: 0xDA00000, data CRC: 0x9A49C90F, OS: Linux, CPU: ARM, image type: OS Kernel Image, compression type: none, image name: ""
440944        0x6BA70         Linux kernel ARM boot executable zImage (little-endian)
458309        0x6FE45         gzip compressed data, maximum compression, from Unix, last modified: 2018-09-20 00:03:05
3233712       0x3157B0        Squashfs filesystem, little endian, version 4.0, compression:gzip, size: 26997354 bytes, 345 inodes, blocksize: 131072 bytes, created: 2018-09-20 00:14:55
```

```
$ binwalk msb15-fw-dec.bin

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
1904552       0x1D0FA8        Mediatek bootloader
1952904       0x1DCC88        Mediatek bootloader
2183997       0x21533D        Certificate in DER format (x509 v3), header length: 4, sequence length: 1284
2184113       0x2153B1        Certificate in DER format (x509 v3), header length: 4, sequence length: 1288
2193608       0x2178C8        CRC32 polynomial table, little endian
2198080       0x218A40        CRC32 polynomial table, little endian
2277936       0x22C230        uImage header, header size: 64 bytes, header CRC: 0x6486887, created: 2018-09-20 00:03:37, image size: 2285568 bytes, Data Address: 0xDA00000, Entry Point: 0xDA00000, data CRC: 0x9A49C90F, OS: Linux, CPU: ARM, image type: OS Kernel Image, compression type: none, image name: ""
2278000       0x22C270        Linux kernel ARM boot executable zImage (little-endian)
2295365       0x230645        gzip compressed data, maximum compression, from Unix, last modified: 2018-09-20 00:03:05
5096544       0x4DC460        Squashfs filesystem, little endian, version 4.0, compression:gzip, size: 72281380 bytes, 2199 inodes, blocksize: 131072 bytes, created: 2018-09-20 00:14:46
77509728      0x49EB460       PNG image, 1920 x 1080, 8-bit/color RGBA, non-interlaced
77509834      0x49EB4CA       Zlib compressed data, best compression
```
