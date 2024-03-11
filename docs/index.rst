Scarfing
========

Motivation
----------

A dummy python package to test out scarf.sh

How to setup
------------

Using poetry:

.. code:: bash

   poetry add scarfing

Using pip:

.. code:: bash

   pip install scarfing

On publishing to pypi
---------------------

1. login to pypi and generate a token
2. poetry config pypi-token.pypi “your-token-here”
3. poetry publish –build

On building the docs
--------------------

1. Follow steps in https://olgarithms.github.io/sphinx-tutorial

   1. Install sphinx
   2. sphinx-quickstart docs
   3. add extensions to docs/conf.py
   4. update theme in docs/conf.py

2. Export README.md to index.rst

   1. pandoc README.md -o docs/index.rst

3. add .readthedocs.yml
4. create a requirements.txt file in docs

   1. poetry export -f requirements.txt –output docs/requirements.txt
      –group docs

5. push to github

On publishing docs to readthedocs
---------------------------------

1. Create a project on readthedocs
2. View the docs

Testing scarf.sh
----------------

-  Run with extra-index-url:

   -  pip install scarfing –extra-index-url
      https://my-test-organization.gateway.scarf.sh/simple/
   -  It will usually take 30 minutes and up to 2-3 hours before you see
      data pulled in.

-  If you run withouth the extra-index-url, it will not pull in data
   from scarf.sh
