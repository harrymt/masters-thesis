# Makefile to generate stats about a latex document
DIRECTORY=chapters
OUTPUT=stats.md

all: setup wordcount wc
	cat $(OUTPUT)

wordcount:
	printf "## Actual count\n" >> $(OUTPUT) &&\
	perl latexcount.pl $(DIRECTORY)/*.tex >> $(OUTPUT)

wc:
	printf "## wc\n" >> $(OUTPUT) &&\
	wc -w $(DIRECTORY)/*.tex | grep total >> $(OUTPUT)

setup:
	printf "# Statistics\n\n" > $(OUTPUT) &&\
	printf "Information about the directory '$(DIRECTORY)'.\n\n" >> $(OUTPUT)

# perl latexcount.pl foo.tex