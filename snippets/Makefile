SHELL := /bin/bash

# Aggregate every *.tex snippet (except aggregated.tex itself)
aggregate:
	@echo "🔄 Regenerating aggregated.tex ..."
	@rm -f aggregated.tex
	@touch aggregated.tex                  # create the file so redirection never fails
	@shopt -s nullglob; \
	files=( *.tex ); \
	if [ $${#files[@]} -eq 0 ]; then \
		echo "⚠️  No .tex snippets found. Write one first, then run 'make aggregate'."; \
	else \
		for f in "$${files[@]}"; do \
			[ "$$f" = "aggregated.tex" ] && continue; \
			printf '\\input{snippets/%s}\n' "$$f" >> aggregated.tex; \
		done; \
		echo "✅ Done. Current line count = $$(wc -l < aggregated.tex)"; \
	fi
