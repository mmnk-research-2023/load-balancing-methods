PDF = index.pdf
MAIN = main
FLAGS =

all:
	make bib

$(PDF) : $(MAIN).tex *.tex
	pdflatex $(FLAGS) $<
	pdflatex $(FLAGS) $<
	mv $(MAIN).pdf $(PDF)

bib: $(MAIN).tex *.tex
	pdflatex $(FLAGS) $<
	biber $(MAIN).bcf
	pdflatex $(FLAGS) $<
	pdflatex $(FLAGS) $<
	mv $(MAIN).pdf $(PDF)
	make clean

clean:
	rm  *.aux *.log *.out *.toc *.bbl *.blg $(MAIN).bcf $(MAIN).run.xml

.PHONY: clean, bib
