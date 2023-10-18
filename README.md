# MicMac

## Official Documentation

This repository contains the official documentation of MicMac software.

The user interested on reading only the main documentation can just download the following file :
- Documentation/DocMicMac.pdf

Specialized documentation can be found here :
- Structureless Global Bundle Adjustment : Documentation/DocMicMac/DocMartini/DocMartini.pdf
- Processing Corridor Geometry Acquisitions : Documentation/DocCaseCorridor/DocCaseCorridor.pdf
- Image Processing Library : Documentation/DocMicMac/DocELISE/DocELISE.pdf
- Perform Non-Regression Testing : Documentation/DocMicMac/DocTripleSec/DocTripleSec.pdf
- MicMac Graphical Interface : Documentation/DocGIMMI/
- Documentation/DocProg/

Some Useful Tutorials :
- Image correlation by Giang NGUYEN            : Documentation/Tutorials/Correlation/Image_Correlation.pdf
- Least Square Estimation by Giang NGUYEN      : Documentation/Tutorials/LSQMatching/LSQ.pdf
- Satellite Image Processing by Ewelina RUPNIK : Documentation/Tutorials/TutoJupyter

Some charts to get used to MicMac main commands : Documentation/Useful_Commands

Some useful (.xm) file : Documentation/FilesSamples

Some useful data : Documentation/Data

Some photogrammetric datasets are available [Here](https://micmac.ensg.eu/index.php/Datasets)



 

## Other resources :

- [MicMac subreddit]([http://forum-micmac.forumprod.com/](https://www.reddit.com/r/MicMac/) 
- [MicMac Wiki](https://micmac.ensg.eu/index.php/Accueil)



## Dependencies
| pdflatex |
| bibtex |
| Ghostscript |

To build the documentation :
```sh
git clone https://github.com/micmacIGN/Documentation.git
cd Documentation/DocMicMac/
make && make clean
```


## License

CECILL-B
