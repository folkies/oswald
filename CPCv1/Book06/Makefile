# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
# This is the Makefile for James Oswald's "The Caledonian Pocket Companion" #
# Volume 1 Book 5. We create two versions, for ABC versions 1 & 2< which    #
# have suffixes -V1.abc and -V2.abc to distinguish them.
# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
U=http://trillian.mit.edu/~jc/music/book/JamesOswald/CPC/CPCV1/Book06

all: CPCv1b06 

CPCv1b06: CPCv1b06-V1 CPCv1b06-V2

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

neat:         ; /bin/rm -f *- *.bak
clean:    neat; /bin/rm -f *.ps *.pdf
clobber: clean; /bin/rm -f CPC*.abc

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

CPCv1b06: CPCv1b06-V1 CPCv1b06-V2

# Format using jcabc2ps:
CPCv1b06-V1: CPCv1b06-V1.abc CPCv1b06-V1.pdf
CPCv1b06-V1= [0-9][0-9][0-9][0-9][0-9][-_]*.abc
CPCv1b06-V1.abc: $(CPCv1b06-V1)
	abcjoin +C $(CPCv1b06-V1) >CPCv1b06-V1.abc
#	sleep 1
CPCv1b06-V1.ps: CPCv1b06-V1.abc fmt/V1.fmt
	jcabc2ps +k2 +Ffmt/V1.fmt +n +x CPCv1b06-V1.abc \
	|PShdr %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >CPCv1b06-V1.ps
CPCv1b06-V1.pdf: CPCv1b06-V1.ps
	ps2pdf CPCv1b06-V1.ps CPCv1b06-V1.pdf

# Format using abcm2ps:
CPCv1b06-V2: CPCv1b06-V2.abc CPCv1b06-V2.pdf
CPCv1b06-V2= [0-9][0-9][0-9][0-9][0-9][=_]*.abc
CPCv1b06-V2.abc: $(CPCv1b06-V2)
	abcjoin +C $(CPCv1b06-V2) >CPCv1b06-V2.abc
CPCv1b06-V2.ps: CPCv1b06-V2.abc fmt/V2.fmt
	abcm2ps -x -F fmt/V2.fmt CPCv1b06-V2.abc -O tmp.ps
	PShdr <tmp.ps %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >CPCv1b06-V2.ps
	/bin/rm tmp.ps
CPCv1b06-V2.pdf: CPCv1b06-V2.ps
	ps2pdf CPCv1b06-V2.ps CPCv1b06-V2.pdf

# Install in the parent directory:
install: ../CPCv1b06-V1.abc ../CPCv1b06-V2.abc
../CPCv1b06-V1.abc: CPCv1b06-V1.abc
	ln -f CPCv1b06-V1.abc ../CPCv1b06-V1.abc
../CPCv1b06-V2.abc: CPCv1b06-V2.abc
	ln -f CPCv1b06-V2.abc ../CPCv1b06-V2.abc

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

