NAME=222
HOME=../..

include ../makefile.sys

all: epub pdf authors

epub: clean fonts version
	mkdir -p dest
	cat $(HOME)/bib/*.bib > dest/all.bib
	bookmanager $(NAME).yaml get
	mv dest/vonLaszewski-$(NAME).epub $(HOME)/docs

pdf:
	ebook-convert \
	  $(HOME)/docs/vonLaszewski-$(NAME).epub \
	  $(HOME)/docs/vonLaszewski-$(NAME).pdf

bib:
	mkdir -p dest
	cp $(HOME)/bib/*.bib dest

version:
	TZ=":US/Eastern"; date > $(HOME)/chapters/version.md

view:
	-killall Books
	$(OPEN_EPUB) $(HOME)/docs/vonLaszewski-$(NAME).epub

authors:
	$(HOME)/bin/authors.py > $(HOME)/chapters/authors.md

fonts:
	#mkdir -p dest/book/
	#-cp -r ../../../bookmanager/bookmanager/template/epub/fonts dest/book/fonts
	echo "ignoring font embedding"

clean:

	rm -rf dest

include ../Makefile.bibtex
