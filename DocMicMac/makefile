NAME = DocMicMac

FTEX=$(NAME).tex\
	Generalites/Intro.tex\
	Generalites/SomReal.tex\
	Generalites/QuickStart.tex\
	Generalites/QuickStart_Apero.tex\
	Generalites/QuickStartOthers.tex\
	Generalites/QuickStartSimplified-Tools.tex\
	Generalites/QuickStartSimplified-Tools-2.tex\
	Generalites/ParamSpec.tex\
	Generalites/FullAutomaticTools.tex\
	Generalites/NameFileSpec.tex\
	Generalites/InteractiveTool.tex\
	Generalites/UseCase2D.tex\
	Generalites/ImageFilter.tex\
	DocRef/ConvTool.tex\
	DocRef/GeoLocalisation.tex\
	DocRef/Advanced-TieP.tex\
	DocRef/Advanced-Apero1.tex\
	DocRef/Advanced-MicMac1.tex\
	DocRef/Advanced-MicMac2.tex\
	DocAlgo/DAMultiRes.tex\
	DocAlgo/DAGeneralites.tex\
	DocAlgo/DACorrel.tex\
	DocAlgo/DAEnergetik.tex\
	DocAlgo/DSensibility.tex\
	DocAlgo/DAOrient.tex\
	DocUtil/DUBins.tex\
	DocUtil/DUMec.tex\
	DocUtil/DUMecaGen.tex\
	DocUtil/DUAutreSec.tex\
	Annexes/Formats.tex\
	Annexes/Vrac3.tex\
	bibliographie.bib

$(NAME).pdf : $(FTEX)
	pdflatex $(NAME)
	bibtex $(NAME)
	pdflatex $(NAME)
	pdflatex $(NAME)

$(NAME).dvi : $(FTEX)
	latex $(NAME)

clean :
	find . -iname "*.aux" -exec rm {} +
		gs -dPrinted=false -sDEVICE=pdfwrite -dCompatibilityLevel=1.5 -dPDFSETTINGS=/ebook -dDownsampleColorImages=true -dColorImageResolution=300 -dNOPAUSE -dQUIET -dBATCH -sOutputFile=foo.pdf $(NAME).pdf
	rm -f $(NAME).blg $(NAME).toc $(NAME).bbl $(NAME).out $(NAME).log $(NAME).pdf
	mv foo.pdf ../$(NAME).pdf
