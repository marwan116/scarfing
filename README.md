# Scarfing

## Motivation
A dummy python package to test out scarf.sh

## How to setup (untracked)

Using poetry:

```bash
poetry add scarfing
```

Using pip:

```bash
pip install scarfing
```

Using docker:

```bash
docker pull ortamina/scarfing:0.1.0
```


## How to setup (tracked)

Using poetry:

```bash
poetry add scarfing --extra-index-url https://my-test-organization.gateway.scarf.sh/simple/
```

Using pip:

```bash
pip install scarfing --extra-index-url https://my-test-organization.gateway.scarf.sh/simple/
```

Using docker:

```bash
docker pull my-test-organization.docker.scarf.sh/ortamina/scarfing:0.1.0
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

## On building/running/pushing docker image
- Build the image:
  - docker build -t scarfing:0.1.0 .
- Run the image to test it
  - docker run -rm --it scarfing:0.1.0  
- Push the image to repository
  - docker tag scarfing:0.1.0 ortamina/scarfing:0.1.0
  - docker push ortamina/scarfing:0.1.0

## Testing scarf.sh 

### python package tracking
- Create a python package on scarf.sh
- Run with extra-index-url:
  - pip install scarfing --extra-index-url https://my-test-organization.gateway.scarf.sh/simple/
  - It will usually take 30 minutes and up to 2-3 hours before you see data pulled in.
- If you run withouth the extra-index-url, it will not register in scarf.sh

### docker image tracking
- Create a docker image on scarf.sh
- Run with the following command:
  - docker pull my-test-organization.docker.scarf.sh/ortamina/scarfing:0.1.0
- It will usually take 30 minutes and up to 2-3 hours before you see data pulled in.
- If you run docker pull ortamina/scarfing:0.1.0, it will not register in scarf.sh

### Adding a pixel to the README
- Create a pixel on the scarf.sh dashboard
  - Specify which package you to correlate the data with (e.g. python or docker)
- Embed the pixel in the README (see pixel image below)
- Unfortunately pandoc does not support moving images to rst, so we need to manually add the pixel to the index.rst file

<img referrerpolicy="no-referrer-when-downgrade" src="https://static.scarf.sh/a.png?x-pxid=038ca666-efd5-46a6-ae08-e4f7bdb244a3" />