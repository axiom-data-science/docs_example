# How to make docs

Add to docs by making new notebook or markdown pages and storing them in this directory. 

If you pre-run your notebooks and save the outputs, you can use `jupyter_execute_notebooks = "off"` to just render what is already in your notebook.
If you don't pre-run your notebooks and don't save the outputs, you can have Myst-NB run them with `jupyter_execute_notebooks = "auto"` (or other options available, see https://myst-nb.readthedocs.io/en/v0.9.0/use/execute.html).

Add new pages by name to `index.rst`.

Make docs locally with

    make html

Look at files at `_build/html/index.html`.

Can push locally-compiled docs to the GitHub Pages site (instead of using Read the Docs) associated with your repository with the following. If you do this, the pages are available at https://axiom-data-science.github.io/docs_example.

    ghp-import -n -p -f _build/html