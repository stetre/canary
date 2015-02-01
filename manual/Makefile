
Tgt  := manual

Stylesdir  = ./
Stylesheet = golo.css
Style = -a stylesheet=$(Stylesheet) -a stylesdir=$(Stylesdir)
Style = 

ifdef Tgt
# one file only
Src = $(Tgt).adoc
else
# all .adoc files
Src  := $(wildcard *.adoc)
endif

Xml  := $(Src:.adoc=.xml)
Html := $(Src:.adoc=.html)
Pdf  := $(Src:.adoc=.pdf)


default: html

check:

clean:
	@-rm -f *~
	@-rm -f *.pdf
	@-rm -f *.pdfmarks
	@-rm -f *.xml
	@-rm -f *.html
	@-rm -f *.epub
	@-rm -f *.fo
	@-rm -f *.log

install:

html: clean
	@asciidoctor $(Style)  $(Src)

preview: html
	@google-chrome $(Html)

docbook: clean
	@asciidoctor -b docbook -d book $(Src)

pdf: clean
	@asciidoctor-pdf -a pdf-style=asciidoctor $(Src)

doc: html pdf
