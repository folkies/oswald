# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
# This is the Makefile for James Oswald's "The Caledonian Pocket Companion" #
# volume 2. The name Robert Bremner is also on the title page, but it's not #
# clear which role(s) each may have played.                                 #
# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #
U=http://trillian.mit.edu/~jc/music/book/James_Oswald/CPC/CPCv2

all: James_Oswald_CPCv2 install

James_Oswald_CPCv2: James_Oswald_CPCv2-V1 James_Oswald_CPCv2-V2

# Format using jcabc2ps:
James_Oswald_CPCv2-V1: James_Oswald_CPCv2-V1.abc James_Oswald_CPCv2-V1.ps James_Oswald_CPCv2-V1.pdf
James_Oswald_CPCv2-V1= [0-9][0-9][0-9][0-9][0-9][-_]*.abc
James_Oswald_CPCv2-V1.abc: $(James_Oswald_CPCv2-V1)
	abcjoin +CS2 $(James_Oswald_CPCv2-V1) >James_Oswald_CPCv2-V1.abc
#	sleep 1
James_Oswald_CPCv2-V1.ps: James_Oswald_CPCv2-V1.abc fmt/V1.fmt
	jcabc2ps +k2 +Ffmt/V1.fmt +n +x James_Oswald_CPCv2-V1.abc \
	|PShdr %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >James_Oswald_CPCv2-V1.ps
James_Oswald_CPCv2-V1.pdf: James_Oswald_CPCv2-V1.ps
	ps2pdf James_Oswald_CPCv2-V1.ps James_Oswald_CPCv2-V1.pdf

# Format using abcm2ps:
James_Oswald_CPCv2-V2: James_Oswald_CPCv2-V2.abc James_Oswald_CPCv2-V2.ps James_Oswald_CPCv2-V2.pdf
James_Oswald_CPCv2-V2= [0-9][0-9][0-9][0-9][0-9][=_]*.abc
James_Oswald_CPCv2-V2.abc: $(James_Oswald_CPCv2-V2)
	abcjoin +CS2 $(James_Oswald_CPCv2-V2) >James_Oswald_CPCv2-V2.abc
James_Oswald_CPCv2-V2.ps: James_Oswald_CPCv2-V2.abc fmt/V2.fmt
	abcm2ps -x -F fmt/V2.fmt James_Oswald_CPCv2-V2.abc -O tmp.ps
	PShdr <tmp.ps %P "James Oswald's Caledonian Pocket Companion v.2" %P \
	|PSftr %D $U/ %D >James_Oswald_CPCv2-V2.ps
	/bin/rm tmp.ps
James_Oswald_CPCv2-V2.pdf: James_Oswald_CPCv2-V2.ps
	ps2pdf James_Oswald_CPCv2-V2.ps James_Oswald_CPCv2-V2.pdf

neat:         ; /bin/rm -f *- *.bak
clean:    neat; /bin/rm -f *.ps *.pdf
clobber: clean; /bin/rm -f James_Oswald_CPCv2-V*.abc

# Install in the ../book/James_Oswald/ and ../book/ directories:
install: ../James_Oswald_CPCv2-V1.abc ../James_Oswald_CPCv2-V2.abc 
../James_Oswald_CPCv2-V1.abc: James_Oswald_CPCv2-V1.abc
	ln -f James_Oswald_CPCv2-V1.abc ../James_Oswald_CPCv2-V1.abc
../James_Oswald_CPCv2-V2.abc: James_Oswald_CPCv2-V2.abc
	ln -f James_Oswald_CPCv2-V2.abc ../James_Oswald_CPCv2-V2.abc

# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = #

# Highland Battle Set, a set of tunes on pages 68-69, commemmorating an unnamed battle
Highland_Battle_Set: Highland_Battle_Set.abc Highland_Battle_Set.pdf
Highland_Battle_Set= 20680_a_Highland_Battle.abc \
	20681_the_March.abc \
	20682_They_Mend_their_Pace.abc \
	20683_the_Battle_begins.abc \
	20684_the_Height_of_the_Battle.abc \
	20685_the_Preparation_for_a_Retreat.abc \
	20691_the_Chief_is_Killed.abc \
	20692_the_Retreat.abc \
	20693_the_Lamentation_for_the_cheif.abc \
	20694_fine.abc
Highland_Battle_Set.abc: $(Highland_Battle_Set)
	abcjoin +C +RS $(Highland_Battle_Set) >Highland_Battle_Set.abc
#	ln -f Highland_Battle_Set.abc set/
Highland_Battle_Set.ps: Highland_Battle_Set.abc fmt/V1.fmt
	jcabc2ps Highland_Battle_Set.abc +Ffmt/V1.fmt \
	|PShdr 'Highland Battle Set' '' 'Highland Battle Set' \
	|PSftr '%P' $U/ '%D' >Highland_Battle_Set.ps
Highland_Battle_Set.pdf: Highland_Battle_Set.ps
	ps2pdf Highland_Battle_Set.ps Highland_Battle_Set.pdf

