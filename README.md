# Silesia compression corpus

## Standard lossless data compression corpora

Three well-known data sets are used by researchers in the universal lossless data compression field. The first one, the Calgary corpus, was introduced in 1989 by Bell et al.. The files in the corpus were chosen to cover up the typical types of data used in computer processing. This corpus is rather old, and it contains some types of data which went out of use, but the corpus is still a good benchmark used by many authors. The corpora proposed later, the Canterbury corpus and the large Canterbury corpus, contain files of similar sizes, less than 5 MB.

Over the years of using of these corpora some observations have proven their important disadvantages. The most important in our opinion are:

- the lack of large files—at present we work with much larger files;
- an over-representation of English-language texts—there are only English files in the three corpora, while in practice many texts are written in different languages;
- the lack of files being a concatenation of large projects(e.g., programming projects)—the application sizes grow quite fast and compressing each of the source files separately is impractical presently; a more convenient way is to concatenate the whole project and to compress the resulting file;
- absence of medical images—the medical images must not undergo a lossy compression because of law regulations;
- the lack of databases that currently grow considerably fast—databases are perhaps the fastest growing type of data.

## Silesia corpus

The intention of the Silesia corpus is to provide a data set of files that covers the typical data types used nowadays. The sizes of the files are between 6 MB and 51 MB.

The chosen files are of different types and come from several sources. In our opinion, nowadays the two fastest growing types of data are multimedia and databases. The former are typically compressed with lossy methods so we do not include them in the corpus. The database files, osdb, sao, nci, come from three different fields. The first one is a sample database from an open source project that is intended to be used as a standard, free database benchmark. The second one, sao, is one of the astronomical star catalogues. This is a binary database composed of records of complex structure. The last one, nci, is a part of the chemical database of structures.

The sizes of computer programs are also growing rapidly. The standard corpora include only single, small routines, both in source and object code. Today it is almost impractical to compress every single source code file separately. The projects are composed of hundreds or thousands files, so it is a common habit to compress it all together. We often can achieve a better compression ratio if we compress a concatenated file of similar contents than the small separate ones. This trend is reflected in including a samba file. Besides the source codes, there is also a need to store the executables. We decided to include two files: ooffice and mozilla. The first one is a single medium-sized executable for the Windows system. The second is a concatenation of the whole application for Tru64 Unix system composed of executables, archives, texts, HTML files, and other.

There are also types of images that cannot be compressed loosely—the medical images. The sizes of such files are also huge and we include two examples of them in the corpus. The first file, x-ray, is an X-ray picture of a child's hand. The second file, mr, is a magnetic resonance, three dimensional image of a head.

The standard corpora contain text files. Moreover, these files are typically the largest files of them, but in our opinion there is a need to test the compression efficiency also on the larger ones stored in different file types. We propose three such files. The first, dickens, is a collection of some works by Charles Dickens that can be found in the Project Gutenberg. This is a plain text file. The second one, reymont, is a book Chlopi by Wladyslaw Reymont stored in a PDF file. The PDF files can be internally-compressed but the quality of this build-in compression is rather poor, and much better results can be obtained when we compress an uncompressed PDF file. Because of this we enclose the uncompressed version. The last text file, webster, is an electronic version of The 1913 Webster Unabridged Dictionary taken from the Project Gutenberg. The file is stored in the HTML format. The last file of the new corpus, xml, is a concatenation of 21 XML files. The XML standard is designed to be a universal file format for storing documents, so we decided to enclose it.

## Silesia Corpus contents

Filename|Description|Type|Source|Raw size [B]|Bzipped size [B]
:-|:-|:-:|:-|-:|-:|
dickens|Collected works of Charles Dickens|English text|Project Gutenberg|10,192,446|2,799,528
mozilla|Tarred executables of Mozilla 1.0 (Tru64 UNIX edition)|exe|Mozilla Project|51,220,480|17,914,392
mr|Medical magnetic resonanse image|picture|Hospital image|9,970,564|2,441,280
nci|Chemical database of structures|database|CACTVS Chemical Information Services at LMC/NCI|33,553,445|1,812,734
ooffice|A dll from Open Office.org 1.01|exe|Open Office|6,152,192|2,862,526
osdb|Sample database in MySQL format from Open Source Database Benchmark|database|Open Source Database Benchmark Project|10,085,684|2,802,792
reymont|Text of the book Chlopi by Wladyslaw Reymont|Polish pdf|Virtual Library of Polish Literature|6,627,202|1,246,230
samba|Tarred source code of Samba 2-2.3|src|Samba Project|21,606,400|4,549,790
sao|The SAO star catalog|bin data|Astronomical Catalogs and Catalog Formats|7,251,944|4,940,524
webster|The 1913 Webster Unabridged Dictionary|html|Project Gutenberg|41,458,703|8,644,714
xml|Collected XML files|html|XMLPPM: XML-Conscious PPM Compression|5,345,280|441,186
x-ray|X-ray medical picture||Hospital image|8,474,240|4,051,112
Total||||211,938,580|54,506,808

## Silesia Corpus details

### dickens

Charles Dickens wrote many novels. The file is a concatenation of some, fourteen, of his works that can be found in the Project Gutenberg (A Child's History Of England, All The Year Round: Contributions, American Notes, The Battle Of Life, Bleak House, A Christmas Carol, David Copperfield, Dombey And Son, Doctor Marigold, Going Into Society, George Silverman's Explanation, Barnaby Rudge: a tale of the Riots of 'eighty, The Chimes, The Cricket On The Hearth). The file is a simple text.

MD5: 88334708559f6db57d79096bc0aca07e

### mozilla

A Mozilla 1.0 open source web browser was installed on the Tru64 UNIX operating system and then the contents of the Mozilla.org directory were tarred. There are 525 files of such types as: executables, jar archives, HTML, XML, text, and others.

MD5: c7789a2097f1ff944b0c737430a339b3

### mr

A magnetic resonanse medical picture of a head. This file is stored is DICOM format and contains 19 planes.

MD5: 38e623e3093b7bf2003ca4b1bbc19927

### nci

The chemical databases of strucures contain information of structures, their components, 2D and/or 3D coordinates, properites, etc. The file is a part of the August 2000 2D File stored in an SDF format which is common file format developped to handle a list of molecular structures associated with properties. The original database is of size 982MB so we had to truncate it to be suitable for a part of the corpus. The 32MB piece (rounded down to the nearest end of the record), we have chosen, is taken from the middle of the original file (starting at the first record after leaving 400MB of data).

MD5: 31f85bc8706f3c921104e7c169e2e2e1

### ooffice

An Open Office is an open source project, which is composed of the word processor, spreadsheet program, presentation maker, and graphical program. The file is a dynamic linked linbrary from version 1.01.

MD5: 573c4ae915e36631d8f2dcffb9b9b66d

### osdb

An Open Source Database Benchmark is a project invented to provide a free test for database systems. One of the parts of the project are sample databases. The 40MB benchmark was run on the MySQL 3.23 server. The file is one of the MySQL database files, hundred.med.

MD5: e734b0c48e6a982adfb5802da3032ecd

### reymont

A book Chlopi by Wladyslaw Reymont was honoured the Nobel Price in 1924. The text of the book was taken from the Virtual Library of Polish Literature. Then it was converted to the LaTeX files from which the uncompressed PDF file was produced. The file is uncompressed due to the fact the built-in compression in PDF format is rather poor, and much better results can be obtained when we compress the uncompressed PDF files.

MD5: d8f54d78105079775f32d76dc55fc671

### samba

Samba is an open souce project that is intended to be a free alternative to the SMB/CIFS clients. The file contains tarred source code (also documentation, graphics) of the Samba 2.2-3 version.

MD5: 154eaea7ea70e89f6339ff0abf4112ca

### sao

There are many star catalogs containing the data of sky objects. The chosen one, SAO catalog, is suitable especially for the amator astronomers. It contains the information about 258,996 stars, and is composed of binary records.

MD5: 79e95a22e18cd82b7e42bf91b380d30b

### webster

The 1913 Webster Unabridged Dictionary is an English dictionary stored in a rather simple HTML. The file is a concatenation of files that can be obtained from Project Gutenberg.

MD5: 474931ad907ac27bf962c75ded46c069

### xml

The XML is an incomming standard of document format. The importance of XML is still growing. The file is a corpus prepared for XMLPPM: XML-Conscious PPM Compression. This is a concatenation of all, eleven, files.

MD5: 9b09c0c80104adb8aae910b7d7db003e

### x-ray

An X-ray medical picture of child's hand. This is a 12-bit gray scaled image.

MD5: 9baec32ad14ec3eff487d254382cb91c