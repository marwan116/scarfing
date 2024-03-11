# Scarfing

## Motivation
A dummy python package to test out scarf.sh

## How to setup

Using poetry:

```bash
poetry add scarfing
```

Using pip:

```bash
pip install scarfing
```

## On publishing to pypi
1. login to pypi and generate a token
2. poetry config pypi-token.pypi "your-token-here"
3. poetry publish --build

## On building the docs
1. Follow steps in https://olgarithms.github.io/sphinx-tutorial
   1. Install sphinx
   2. sphinx-quickstart docs
   3. add extensions to docs/conf.py
   4. update theme in docs/conf.py
2. Export README.md to index.rst
   1. pandoc README.md -o docs/index.rst
2. add .readthedocs.yml
3. create a requirements.txt file in docs
   1. poetry export -f requirements.txt --output docs/requirements.txt --group docs
4. push to github

## On publishing docs to readthedocs
1. Create a project on readthedocs
2. View the docs


## Testing scarf.sh 

## python package tracking
- Run with extra-index-url:
  - pip install scarfing --extra-index-url https://my-test-organization.gateway.scarf.sh/simple/
  - It will usually take 30 minutes and up to 2-3 hours before you see data pulled in.
- If you run withouth the extra-index-url, it will not pull in data from scarf.sh


## Adding a pixel to the README
- Create a pixel on the scarf.sh dashboard
  - Specify which package you to correlate the data with (e.g. python or docker)
- Embed the pixel in the README (see pixel image below)
- Unfortunately pandoc does not support moving images to rst, so we need to manually add the pixel to the index.rst file

<img referrerpolicy="no-referrer-when-downgrade" src="https://static.scarf.sh/a.png?x-pxid=038ca666-efd5-46a6-ae08-e4f7bdb244a3" />