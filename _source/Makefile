
results.tex:	results.Rnw setup.R
	R CMD Sweave results.Rnw

appendix.tex:	appendix.Rnw setup.R
	R CMD Sweave appendix.Rnw

whatif.bib:	../Bibliography/whatif.bib
	cp ../Bibliography/whatif.bib .

main.pdf: main.tex results.tex methods.tex appendix.tex introduction.tex discussion.tex whatif.bib abstract.tex 
	texi2dvi --pdf main.tex
	pdflatex main.tex

all: main.pdf

clean:
	rm -rf *~
	rm -rf *doc
	rm -rf *fff
	rm -rf *log
	rm -rf results.tex
	rm -rf appendix.tex
	rm -rf *pdf
	rm -rf *tgz
	texclean main.tex
	rm -rf *aux
	rm -rf *bbl
	rm -rf *tpt

	
