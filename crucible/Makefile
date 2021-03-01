PREFIX?=template
FILE?=files/$(PREFIX).tex
SRC?=$(FILE)
HEAD?=headers/$(PREFIX).tex
VERBOSE?=
BIB?=
PAUSE?=
SUFFIX?=

export TEXINPUTS:=../../tex//:../src//:${TEXINPUTS}
pdf: guard-SRC guard-PREFIX
	@ if [ "$(VERB_CMD)" != "" ]; \
	  then \
		  printf "%s" "Compiling $(PREFIX)$(SUFFIX).pdf ..."; \
	  fi
	@pdflatex --jobname="$(PREFIX)$(SUFFIX)" '\input{$(SRC)}' $(VERB_CMD)
	@printf "%s" ":"
	@pdflatex --jobname="$(PREFIX)$(SUFFIX)" '\input{$(SRC)}' $(VERB_CMD)
	@cp $(PREFIX)$(SUFFIX).pdf ../outbox/$(PREFIX)$(SUFFIX).pdf
	@echo "[../outbox/$(PREFIX)$(SUFFIX).pdf]"

slides: guard-PREFIX guard-HEAD
	@ if [ "$(VERB_CMD)" != "" ]; \
	  then \
	    if [ "$(PAUSE)" = ",handout" ]; then \
		  printf "%s" "Compiling $(PREFIX)$(SUFFIX).pdf on handout mode..."; \
		else \
		  printf "%s" "Compiling $(PREFIX)$(SUFFIX).pdf ..."; \
		fi \
	  fi
	@pdflatex --jobname="$(PREFIX)$(SUFFIX)" '\documentclass[aspectratio=169$(PAUSE)]{beamer} \newcommand{\PREFIX}{$(PREFIX)}\input{$(HEAD)}\begin{document}{\setbeamercolor{background canvas}{bg=firstpageBottom}\frame[plain]{\mkTitle}}\input{$(FILE)}\end{document}' $(VERB_CMD)
	@printf "%s" ":"
	@pdflatex --jobname="$(PREFIX)$(SUFFIX)" '\documentclass[aspectratio=169$(PAUSE)]{beamer}\newcommand{\PREFIX}{$(PREFIX)}\input{$(HEAD)}\begin{document}{\setbeamercolor{background canvas}{bg=firstpageBottom}\frame[plain]{\mkTitle}}\input{$(FILE)}\end{document}' $(VERB_CMD)
	@cp $(PREFIX)$(SUFFIX).pdf ../outbox/$(PREFIX)$(SUFFIX).pdf
	@echo "[../outbox/$(PREFIX)$(SUFFIX).pdf]"


guard-%:
	@ if [ "${${*}}" = "" ]; then \
		echo "Environment variable $* not set"; \
	exit 1; \
fi

snapshot:
	@git add ..
	@sleep 0.5
	@read -p "Snapshot, " STUFF; \
	git commit -m "Snapshot, $$STUFF"
