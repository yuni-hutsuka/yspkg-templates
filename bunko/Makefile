.PHONY: all
all:
	make title.pdf
	make colophon.pdf
	make main.pdf
	make bundle.pdf
	make cropmark.pdf
	make bunko-title.pdf

.PHONY: cleanup
cleanup:
	cd _typesetting/ && rm -rv *.aux *.bbl *.blg *.bst *.fdb_latexmk *.fls *.idx *.ilg *.ind *.lof *.log *.lol *.lot *.ltjruby *.nav *.out *.snm *.toc *.xmpi *.pdf

title.pdf: _typesetting/title.tex
	cd _typesetting && latexmk title.tex

main.pdf: _typesetting/main.tex
	cd _typesetting && latexmk main.tex

colophon.pdf: _typesetting/colophon.tex
	cd _typesetting && latexmk colophon.tex

bundle.pdf: title.pdf main.pdf colophon.pdf
	pdfunite \
		_typesetting/title.pdf \
		_typesetting/main.pdf \
		_typesetting/colophon.pdf \
		_typesetting/bundle.pdf

cropmark.pdf: _typesetting/bundle.pdf
	cd _typesetting && latexmk cropmark.tex

bunko-title.pdf: _typesetting/cropmark.pdf
	mv _typesetting bunko-title/bunko-title.pdf
