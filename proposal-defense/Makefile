SHELL=/bin/bash
MAIN=main
LATEX=pdflatex -shell-escape
BIBER=biber
DTM=$(shell date +%Y%m%d-%H%M%S)

all: clean build clear

build:
	$(LATEX) $(MAIN).tex
	$(BIBER) $(MAIN)
	$(LATEX) $(MAIN).tex
	$(LATEX) $(MAIN).tex

clean:
	@rm -f $(MAIN).{pdf,ps,log,lot,lof,toc,out,dvi,bbl,bcf,run.xml,blg} *.aux
	@echo Cleared all temporary files and $(MAIN).pdf

clear:
	@rm -f $(MAIN).{ps,log,lot,lof,toc,out,dvi,bbl,blg} *.aux
	@echo Cleared all temporary files

draft:
	@cp $(MAIN).pdf $(MAIN)-draft-$(DTM).pdf
	@echo Saved the draft as: $(MAIN)-draft-$(DTM).pdf
