# README

These instructions will help setup you

1. Creating the virtual environment. 

Input these commands into terminal:

pip install virtualenv
virtualenv venv

2. Activate the virtualenv.

Input this command into terminal:

source venv/bin/activate

### User Defined Python Packages

1. Create a project and include the necessary resources for a python project. For python to recognize folders and scripts within your package, you should be including the `__init__.py` scripts in each folder. You can learn more about user defined python packages [here](https://www.learnpython.org/en/Modules_and_Packages) and additional usages of `__init__.py` to include more setup information.
```
└───project
│   └───package
│       └───data
|           |   utils.py
|           |   __init__.py
│       └───api
|           |   scrape.py
|           |   __init__.py
|       |   __init__.py
│   │   setup.py (package setup script)
```

2. You need to create a proper `setup.py` script that includes the package information.

```py
try:
    from setuptools import setup, find_packages
except ImportError:
    from distutils.core import setup

config = {
    'description': 'package description',
    'author': 'Neil Seward',
    'author_email': 'neil.seward@uoit.ca',
    'version': '0.0.1',
    'packages': find_packages(),
    'name': 'package_name'
}

setup(**config)
```

3. Once you have a good `setup.py` script, you can install your user defined packages.
```
python setup.py build
python setup.py install
```

4. In the `package` sub folder, try installing the reference package to your virtualenv.

### Note:

Python code is placed in api folder, in .ipynb format, so open via jupyter notebook.

