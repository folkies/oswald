# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
# This is the Makefile for James Oswald's "The Caledonian Pocket Companion" #
# Volume  1,  the  combination of his Books 1-6, followed later by Volume 2 #
# with the content of Books 7-12.  There is some  confusion,  because  this #
# series was first published in smal annual booklets sometimes called "Book #
# N" and sometimes "Volume N".  Then he published  larger  books  combining #
# several  of  those  books'  content.   
# In this directory we combine the "books" in the Book01-Book06 directories
# into CPCv1 files.  We actually create separate copies for ABC
# versions 1 and 2, since a few tunes use features only available in ABC2.
# So we use "v1" and "v2" to refer to Oswald's Volumes 1 & 2, and we use 
# "V1" and "V2" to refer to ABC1 and ABC2.
# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
U=http://trillian.mit.edu/~jc/music/book/JamesOswald/CPC/CPCv1

all: CPCv1-V1 CPCv1-V2

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

neat:         ; /bin/rm -f *- *.bak
clean:    neat; /bin/rm -f *.ps *.pdf
clobber: clean; /bin/rm -f CPC*.abc

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

# Format using jcabc2ps:
CPCv1-V1: CPCv1-V1.abc CPCv1-V1.pdf
CPCv1-V1= 10000_Title.abc \
	CPCv1b01-V1.abc \
	CPCv1b02-V1.abc \
	CPCv1b05-V1.abc \
	CPCv1b06-V1.abc
CPCv1-V1.abc: $(CPCv1-V1)
	abcjoin +C $(CPCv1-V1) >CPCv1-V1.abc
CPCv1-V1.ps: CPCv1-V1.abc fmt/V1.fmt
	jcabc2ps +k2 +Ffmt/V1.fmt +n +x CPCv1-V1.abc \
	|PShdr %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >CPCv1-V1.ps
CPCv1-V1.pdf: CPCv1-V1.ps
	ps2pdf CPCv1-V1.ps CPCv1-V1.pdf

# Format using jcabc2ps:
CPCv1-V2: CPCv1-V2.abc CPCv1-V2.pdf
CPCv1-V2= 10000_Title.abc \
	CPCv1b01-V2.abc \
	CPCv1b02-V2.abc \
	CPCv1b05-V2.abc \
	CPCv1b06-V2.abc
CPCv1-V2.abc: $(CPCv1-V2)
	abcjoin +C $(CPCv1-V2) >CPCv1-V2.abc
CPCv1-V2.ps: CPCv1-V2.abc fmt/V2.fmt
	jcabc2ps +k2 +Ffmt/V2.fmt +n +x CPCv1-V2.abc \
	|PShdr %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >CPCv1-V2.ps
CPCv1-V2.pdf: CPCv1-V2.ps
	ps2pdf CPCv1-V2.ps CPCv1-V2.pdf

CPCv1b01-V1.abc: Book01/CPCv1b01-V1.abc; ln -f Book01/CPCv1b01-V1.abc CPCv1b01-V1.abc
Book01/CPCv1b01-V1.abc: ; cd Book01; make CPCv1b01-V1.abc
CPCv1b01-V2.abc: Book01/CPCv1b01-V2.abc; ln -f Book01/CPCv1b01-V2.abc CPCv1b01-V2.abc
Book01/CPCv1b01-V2.abc: ; cd Book01; make CPCv1b01-V2.abc

CPCv1b02-V1.abc: Book02/CPCv1b02-V1.abc; ln -f Book02/CPCv1b02-V1.abc CPCv1b02-V1.abc
Book02/CPCv1b02-V1.abc: ; cd Book02; make CPCv1b02-V1.abc
CPCv1b02-V2.abc: Book02/CPCv1b02-V2.abc; ln -f Book02/CPCv1b02-V2.abc CPCv1b02-V2.abc
Book02/CPCv1b02-V2.abc: ; cd Book02; make CPCv1b02-V2.abc

CPCv1b05-V1.abc: Book05/CPCv1b05-V1.abc; ln -f Book05/CPCv1b05-V1.abc CPCv1b05-V1.abc
Book05/CPCv1b05-V1.abc: ; cd Book05; make CPCv1b05-V1.abc
CPCv1b05-V2.abc: Book05/CPCv1b05-V2.abc; ln -f Book05/CPCv1b05-V2.abc CPCv1b05-V2.abc
Book05/CPCv1b05-V2.abc: ; cd Book05; make CPCv1b05-V2.abc

CPCv1b06-V1.abc: Book06/CPCv1b06-V1.abc; ln -f Book06/CPCv1b06-V1.abc CPCv1b06-V1.abc
Book06/CPCv1b06-V1.abc: ; cd Book06; make CPCv1b06-V1.abc
CPCv1b06-V2.abc: Book06/CPCv1b06-V2.abc; ln -f Book06/CPCv1b06-V2.abc CPCv1b06-V2.abc
Book06/CPCv1b06-V2.abc: ; cd Book06; make CPCv1b06-V2.abc

# Install in the ../book/JamesOswald/ and ../book/ directories:
install: \
	../CPCv1-V1.abc ../../CPCv1-V1.abc \
	../CPCv1-V2.abc ../../CPCv1-V2.abc
../CPCv1-V1.abc: CPCv1-V1.abc
	ln -f CPCv1-V1.abc ../CPCv1-V1.abc
../CPCv1-V2.abc: CPCv1-V2.abc
	ln -f CPCv1-V2.abc ../CPCv1-V2.abc
../../CPCv1-V1.abc: CPCv1-V1.abc
	ln -f CPCv1-V1.abc ../../CPCv1-V1.abc
../../CPCv1-V2.abc: CPCv1-V2.abc
	ln -f CPCv1-V2.abc ../../CPCv1-V2.abc

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

