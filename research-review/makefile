# Makefile to generate stats about a latex document
DIRECTORY=chapters
OUTPUT=stats.md

all: setup wordcount wc todos
	cat $(OUTPUT)

wordcount:
	printf "\n## Actual count\n" >> $(OUTPUT) &&\
	perl latexcount.pl $(DIRECTORY)/*.tex >> $(OUTPUT)

wc:
	printf "## Words with Latex Commands\n\n" >> $(OUTPUT) &&\
	wc -w $(DIRECTORY)/*.tex | grep total >> $(OUTPUT)

todos:
	printf "\n## TODOs Left\n\n" >> $(OUTPUT) &&\
	cat main.tex $(DIRECTORY)/*.tex | grep -c @TODO >> $(OUTPUT)

setup:
	printf "# Statistics\n\n" > $(OUTPUT) &&\
	printf "Information about the directory '$(DIRECTORY)'.\n" >> $(OUTPUT)
