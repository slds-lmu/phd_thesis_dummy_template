TEX    = latex
PDFTEX = pdflatex
BIBTEX = bibtex 
DVIPS  = dvips

INPUTFILES = diss.tex           \
             zusammenfassung.tex\
	     kap_01.tex         \
	     kap_02.tex         \
	     anhang.tex         \
	     danksagung.tex     \
	     literatur.bib

%.aux:	%.tex
	$(TEX)    $<

%.bbl:  %.aux
	$(BIBTEX) $*
	$(BIBTEX) $*

%.dvi:  %.bbl
	$(TEX)    $*
	$(TEX)    $*

%.ps:	%.dvi 
	$(DVIPS)  -o $@ $<

%.pdf: 	%.bbl
	$(PDFTEX) $*
	$(PDFTEX) $*

.phony: clean
clean:	
	$(RM) *~ *.aux *.log *.toc *.blg *.bbl *.lof *lot *.out *.dvi 

all: 	diss.pdf

diss.bbl:$(INPUTFILES)

