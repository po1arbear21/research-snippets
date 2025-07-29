MAIN = main
OUTPUT_DIR = build

.PHONY: all pdf clean open

all: pdf

pdf: $(OUTPUT_DIR)/$(MAIN).pdf

$(OUTPUT_DIR)/$(MAIN).pdf: $(MAIN).tex $(wildcard tex/*.tex) $(wildcard figs/*) $(wildcard bib/*.bib)
	@mkdir -p $(OUTPUT_DIR)
	latexmk -pdf -synctex=1 -output-directory=$(OUTPUT_DIR) $(MAIN).tex

clean:
	latexmk -C -output-directory=$(OUTPUT_DIR)
	rm -rf $(OUTPUT_DIR)

open: pdf
	@if command -v xdg-open > /dev/null; then \
		xdg-open $(OUTPUT_DIR)/$(MAIN).pdf; \
	elif command -v open > /dev/null; then \
		open $(OUTPUT_DIR)/$(MAIN).pdf; \
	else \
		echo "Cannot open PDF: no suitable command found"; \
	fi

watch:
	latexmk -pdf -synctex=1 -output-directory=$(OUTPUT_DIR) -pvc $(MAIN).tex