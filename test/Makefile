# Roland's Make system for LaTeX.

# Compile system.
LX = xelatex
BX = biber

# Project name and file name parts.
PROJECT = SchaeferEinstiegstest
SUFFSUFF = .pdf
FUSUFF = FUBerlin

# TeX Sources to watch.
SOURCES = einstiegstest.tex	 
MAININCLUDE = \input{einstiegstest.tex}

# Stuff passed to XeLaTeX.
FUDEF = \def\FU{}

# XeLaTeX flags.
PREFLAGS = -no-pdf
TEXFLAGS = 

$(PROJECT)$(SUFFSUFF): $(SOURCES)
	$(LX) $(TEXFLAGS) -jobname=$(PROJECT) "$(MAININCLUDE)"

$(PROJECT)$(FUSUFF)$(SUFFSUFF): $(SOURCES)
	$(LX) $(TEXFLAGS) -jobname=$(PROJECT)$(FUSUFF) "$(FUDEF)$(MAININCLUDE)"

.PHONY: normal fu all clean

normal: $(PROJECT)$(SUFFSUFF)

fu: $(PROJECT)$(FUSUFF)$(SUFFSUFF)

all: normal fu

clean:
	\rm -f *.adx *.and *.aux *.bbl *.blg *.idx *.ilg *.ldx *.lnd *.log *.out *.rdx *.run.xml *.sdx *.snd *.toc *.wdx *.xdv *.nav *.snm *.bcf *.vrb

