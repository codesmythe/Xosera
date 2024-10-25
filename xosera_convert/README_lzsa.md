# lzsa - Efficient lossless compression optimized for smaller CPUs

I have placed a "copy" of the lzsa repository here for use by `xosera_convert` utility.
Since git submodules tend to be a pain and this repository fairly stable, I have just duplicated the tree.

The original repository is under the zlib license and is located at: <https://github.com/emmanuel-marty/lzsa>

Here is part of the description of lzsa:

> LZSA is a collection of byte-aligned compression formats that are specifically engineered for very fast decompression on 8-bit systems. It can compress files of any size by using blocks of a maximum size of 64 Kb with block-interdependent compression and up to 64 Kb of back-references for matches.

Even though designed for "8-bit" CPUs since it has relatively good compression and the decompression is very fast and light-weight it seemed a good candidate for basic compression/decompression of Xosera assets.

-Xark
