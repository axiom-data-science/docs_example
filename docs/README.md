# How to make docs

## Running locally

Add to docs by making new notebook or markdown pages and storing them in this directory. 

If you pre-run your notebooks and save the outputs, you can use `jupyter_execute_notebooks = "off"` to just render what is already in your notebook.
If you don't pre-run your notebooks and don't save the outputs, you can have Myst-NB run them with `jupyter_execute_notebooks = "auto"` (or other options available, see https://myst-nb.readthedocs.io/en/v0.9.0/use/execute.html).

Add new pages by name to `index.rst`.

Make docs locally with

    make html

Look at files at `_build/html/index.html`.

Can push locally-compiled docs to the GitHub Pages site (instead of using Read the Docs) associated with your repository with the following. If you do this, the pages are available at https://axiom-data-science.github.io/docs_example.

    ghp-import -n -p -f _build/html


## Convert a notebook to markdown

Use jupytext to convert from notebook to md with myst encoding to be able to compile code:

    jupytext NOTEBOOK.ipynb --to myst

Can convert exactly back from md to notebook with:

    jupytext MD.md --to ipynb


## To additionally use Read the Docs to compile remotely

To enable that the docs are being built for each release, just head over to ReadTheDocs, link your account with github and link your repository.

The only option you need to enable is in [Read the Docs for your project](https://readthedocs.org/projects/docs-example-axds/): 
`Admin > Advanced Settings > Default Settings > Install Project`
(Actually might not want to install if your package isn't really meant to be installed like software)

If you want to have a new version of your docs built for each submitted PR (very helpful when working on the docs themselves), navigate to the project in Read the Docs and click `Admin>Advanced Settings>Build pull requests` for this project.

By default RTD does not trigger a build for releases. So if you want your docs to show your shiny new version of the docs for each release, go to your repo `Settings > Webhooks`, find the readthedocs hook, click on it and add a checkmark for Releases under the "Which events would you like to trigger this webhook?" section.