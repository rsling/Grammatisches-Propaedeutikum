# Roland's Make system for LaTeX.

# Compile system.
LX = xelatex

# Project name and file name parts.
PROJECT = SchaeferGermanistikGrammatikJenaEinstiegstest
OUTDIR = output

# TeX Sources to watch.
SOURCEDIR = .
SOURCES = $(wildcard $(SOURCEDIR)/*.tex)

# Stuff passed to XeLaTeX.
MAININCLUDE = \input{main}
MULOE=\def\SOLUTIONS{}

# XeLaTeX flags.
TEXFLAGS = -output-directory=$(OUTDIR)

# Create output dir if needed.
$(info $(shell [ ! -d $(OUTDIR) ] && mkdir -p ./$(OUTDIR)/includes))


$(PROJECT).pdf: $(SOURCES)
	$(LX) -no-pdf -jobname=$(PROJECT) $(TEXFLAGS) "$(MAININCLUDE)"
	$(LX) -jobname=$(PROJECT) $(TEXFLAGS) "$(MAININCLUDE)"

$(PROJECT)Muloe.pdf: $(SOURCES)
	$(LX) -no-pdf -jobname=$(PROJECT)Muloe $(TEXFLAGS) "$(MULOE)$(MAININCLUDE)"
	$(LX) -jobname=$(PROJECT)Muloe $(TEXFLAGS) "$(MULOE)$(MAININCLUDE)"

# Phony shit.

.PHONY: test muloe all clean

test:	$(PROJECT).pdf

muloe:	$(PROJECT)Muloe.pdf

all:	test muloe

clean:
	cd ./output; rm -f *.adx *.and *.aux *.bbl *.blg *.idx *.ilg *.ldx *.lnd *.log *.out *.rdx *.run.xml *.sdx *.snd *.toc *.wdx *.xdv *.nav *.snm *.bcf *.vrb

