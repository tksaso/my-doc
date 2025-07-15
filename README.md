# my-doc  
Documentation for starting ReadTheDocs!  

1. Create GitHub repository in GitHub  
2. Clone the GitHub repository  
```shell-session  
$ git clone https://github.com/tksaso/my-doc.git  
$ cd my-doc  
```  
3. Setup Python+Sphinx  
```shell-session  
$ python -m venv venv  
$ source  venv/bin/activate  
$ pip3 install sphinx sphinx_rtd_theme myst-parser  
$ sphinx-quickstart docs  
```  
4. Edit the Setting file (docs/conf.py)  
```python:docs/conf.py  
# Configuration file for the Sphinx documentation builder.  
#  
# For the full list of built-in configuration values, see the documentation:  
# https://www.sphinx-doc.org/en/master/usage/configuration.html  

import os  
import sys  
sys.path.insert(0, os.path.abspath('..'))

# -- Project information -----------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#project-information

project = 'Test Doc Page'
copyright = '2025, Tsukasa Aso'
author = 'Tsukasa Aso'

# -- General configuration ---------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#general-configuration

extensions = [
    'myst_parser',
]

templates_path = ['_templates']
exclude_patterns = ['_build', 'Thumbs.db', '.DS_Store']

# -- Options for HTML output -------------------------------------------------
# https://www.sphinx-doc.org/en/master/usage/configuration.html#options-for-html-output

html_theme = 'sphinx_rtd_theme'
html_static_path = ['_static']
```

5. Create a Requirements file  
```:docs/requirements.txt  
sphinx  
sphinx_rtd_theme
myst-parser
```

6. Commit and push to GitHub repository  
```shell-session
$ git add .
$ git commit -m "Initial commit with sphinxs doc"
$ git piush
```

7. Login to readthedocs.org  
```
http://readthedocs.org
```
Login with the GitHub account.  

8. Add a project refering the GitHub repository  
 - [Add a Project] -> Choose the GitHub repository  
 - It requests the prokject name, that should be lile "tksaso-my-doc".  
 - Check the build finished without error  
 - If there are errors, check [build] log.  
 - When everything is OK, access the page with the project name in ReadTheDocs,  
 ```
 https://tksaso-my-doc.readthedocs.io/
 ```
 - This may forward to a page with the build number such as:  
 ```
 https://app.readthedocs.org/projects/tksaso-my-doc/builds/28858583/
 ```

