TEXFILES=clientserver/clientserver.tex sockets/sockets.tex  spodesign/spodesign.tex  tcpip/tcpip.tex

%.html: %.tex $(TEXFILES)
	latex2html -rootdir HTML \
	    -split 6 \
	    -noindex_in_navigation \
	    -title "Лекции по СПОЛКС. Пынькин Д.А." \
	    -prefix spolks_pynkin- \
	    -address 'Пынькин Денис Александрович {denis [dot] pynkin [at] t-linux [dot] by} © 2011<br><a rel="license" href="http://creativecommons.org/licenses/by/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/80x15.png" /></a><br />This <span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" rel="dct:type">work</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/3.0/">Creative Commons Attribution 3.0 Unported License</a>.' \
	    -noinfo \
	    -antialias \
	    -html_version 4.0,latin1,unicode $<

%.dvi: %.tex $(TEXFILES)
	latex $<
	latex $<
	latex $<

%.ps: %.dvi
	dvips -j0 -Ppdf -o $@ $<

%.pdf: %.ps
	ps2pdf $<


all: main.pdf

bib: main.aux
	bibtex8 -s main.aux

