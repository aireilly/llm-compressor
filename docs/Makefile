# Minimal makefile for Sphinx documentation

# You can set these variables from the command line, and also
# from the environment for the first two.
SPHINXOPTS    ?=
SPHINXBUILD   ?= sphinx-build
SOURCEDIR     = source
BUILDDIR      = build

EXAMPLES_SRC  = ../examples
EXAMPLES_DST  = $(SOURCEDIR)/doc

.PHONY: help Makefile copy-examples clean update-index prepare html

# Default target
help:
	@$(SPHINXBUILD) -M help "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)

# Build docs and optionally serve locally
html: clean copy-examples update-index
	@$(SPHINXBUILD) -M html "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
	@if [ -z "$$CI" ]; then \
		echo "Starting local HTTP server at http://localhost:8000"; \
		python3 -m http.server --directory $(BUILDDIR)/html; \
	fi

# Clean build and copied example files
clean:
	@$(SPHINXBUILD) -M clean "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
	rm -rf $(EXAMPLES_DST)

# Copies .md files from ../examples/ to source/doc/, preserving structure
copy-examples:
	rm -rf $(EXAMPLES_DST)
	rsync -av --prune-empty-dirs --include '*/' --include '*.md' --exclude '*' $(EXAMPLES_SRC)/ $(EXAMPLES_DST)

# Updates docs/index.md with current Markdown files
update-index:
	@echo "Generating source/examples.md..."
	@./scripts/copy-examples-docs.sh

# Catch-all target: route all unknown targets to Sphinx using the new
# "make mode" option.  $(O) is meant as a shortcut for $(SPHINXOPTS).
%: Makefile
	@$(SPHINXBUILD) -M $@ "$(SOURCEDIR)" "$(BUILDDIR)" $(SPHINXOPTS) $(O)
