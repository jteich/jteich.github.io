---
redirect_from:
  /blog/2004/09/you-can-create-multi-page-tiff.html
---
You can create a multi-page tiff document by using the tiffcp tool. It is part of the [LibTIFF](http://www.libtiff.org/) tools. Its use is as simple as: 
tiffcp -c lzw a.tif b.tif destination.tif 
where the -c option chooses the compression of the output file, in this case LZW. The a.tif and the b.tif are the files for input, and the last file on the line is the name of the output file. 

Actually, this wont work on my computer that is running Redhat 9.0. This is because support for LZW compression is disabled. Instead, you try '-c packbits' or '-c zip' instead. I was not able to open up a tif file with Microsoft Document Imaging that was compressed with 'zip'. I don't know if the file became corrupted or if Microsoft Document Imaging does not support the zip compression.
