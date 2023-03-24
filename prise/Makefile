.PHONY: all
all:
	make title.pdf
	make colophon.pdf
	make main.pdf
	make prise-title.pdf

.PHONY: cleanup
cleanup:
	cd _typesetting/ && rm -rv *.aux *.bbl *.blg *.bst *.fdb_latexmk *.fls *.idx *.ilg *.ind *.lof *.log *.lol *.lot *.ltjruby *.nav *.out *.snm *.toc *.xmpi *.pdf

title.pdf: _typesetting/title.tex
	cd _typesetting && latexmk title.tex

main.pdf: _typesetting/main.tex
	cd _typesetting && latexmk main.tex

colophon.pdf: _typesetting/colophon.tex
	cd _typesetting && latexmk colophon.tex

prise-title.pdf: title.pdf main.pdf colophon.pdf
	pdfunite \
		_typesetting/title.pdf \
		_typesetting/main.pdf \
		_typesetting/colophon.pdf \
		prise-title/prise-title.pdf
