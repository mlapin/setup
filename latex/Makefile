TARGETS = main.pdf supplement.pdf
PDFLATEX = pdflatex
BIBTEX = bibtex

.PHONY: all clean cleanall

all: $(TARGETS)

%.pdf: %.tex
	$(PDFLATEX) $<
	$(BIBTEX) $(<:.tex=) \
	    && ($(PDFLATEX) $< && $(PDFLATEX) $<) \
	    || echo "BibTeX failed on " $<

clean:
	@rm -vf *.aux *.bbl *.blg *.brf *.dvi *.idx *.log *.lot *.lof *.out \
		*.spl *.toc *.synctex.gz

cleanall: clean
	@rm -vf $(TARGETS)
