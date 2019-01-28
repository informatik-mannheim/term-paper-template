# Makefile for the TPE exam

TEMP_DIR = ../temp
RESULT_DIR = ../result
LATEX = pdflatex
BIBTEX = biber
MAKEINDEX = makeindex

define latex-it
$(eval FILE = $(firstword $^))
cp literatur.bib $(TEMP_DIR)
@echo "Building $(FILE)"
@echo $(FILE)
@$(LATEX) -draftmode -output-directory=$(TEMP_DIR) $(FILE)
@cd $(TEMP_DIR) ; $(BIBTEX) $(basename $(FILE)) 
# @cd $(TEMP_DIR) ; $(MAKEINDEX) $(basename $(FILE)).idx
@$(LATEX) -draftmode -output-directory=$(TEMP_DIR) $(FILE) > /dev/null
@$(LATEX) -draftmode -output-directory=$(TEMP_DIR) $(FILE) > /dev/null
@$(LATEX) -output-directory=$(TEMP_DIR) $(FILE)
endef

.PHONY: all
all: $(TEMP_DIR) $(RESULT_DIR) \
	$(TEMP_DIR)/seminararbeit.pdf \
	$(RESULT_DIR)/seminararbeit.pdf \

.PHONY: clean
clean:
	rm -rf $(TEMP_DIR)
	rm -rf $(RESULT_DIR)

overleaf:
	@cd .. && zip -r term-paper-overleaf.zip tex/*

$(TEMP_DIR)/seminararbeit.pdf: seminararbeit.tex preambel.tex literatur.bib src/* img/*
	$(latex-it)

$(RESULT_DIR)/seminararbeit.pdf: $(TEMP_DIR)/seminararbeit.pdf
	cat $< > $@
 
$(TEMP_DIR):
	mkdir $(TEMP_DIR)

$(RESULT_DIR):
	mkdir $(RESULT_DIR)

