pdf:
	pandoc presentation.md  --slide-level 3 -t beamer -o presentation.tex
	pdflatex MicmacQuick.tex
	pdflatex MicmacQuick.tex

clean:
	rm -f *.aux *.log *.out *.toc *.snm *.nav
