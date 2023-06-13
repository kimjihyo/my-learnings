# Python Dependency Management
While pip alone is often sufficient for personal use, using a dependency management tool is recommended for collaborative projects as it's a higher-level tool that simplifies dependency management for common use cases.

Here are the list of tools for dependency management
- pipenv
- poetry
- conda
- hatch
- micropipenv
- pdm
- pip-tools

## `venv` - Creation of virtual environments
Python "Virtual Environments" allow Python packages to be installed in an isolated location for a particular application, rather than being istalled globally.

## Without a dependency management tool

First create a virtual environment using venv

```
python3 -m venv <DIR>
source <DIR>/bin/activate
```

Next create a `requirements.txt` file that contains a list of items to be installed using pip install. Requirements files are used to hold the result from pip freeze for the purpose of achieving repeatable installs. In this case, your requirements file contains a pinned version of everything that was installed when `pip freeze` was run.

```
python -m pip install numpy
python -m pip freeze > requirements.txt
```

To install dependencies listed in the requirements file:

```
python -m pip install -r requirements.txt
```

Requirements files are used to force pip to properly resolve dependencies. pip 20.2 and earlier doesn't have tru dependency resolution, but instead simply uses the first specification it finds for a project. E.g. if pkg1 requires pkg3>=1.0 and pkg2 requires pkg3>=1.0,<=2.0, and if pkg1 is resolved first, pip will only use pkg3>=1.0, and could easily end up installing a version of pkg3 that conflicts with the needs of pkg2. To solve this problem, you can place pkg3>=1.0,<=2.0 (i.e. the correct specification) into your requirements file directly along with the other top level requirements.

# setup.py vs Dependency Managemnt tools

Pipenv and Pipfile are useful for every project. They are useful internal tools for easing development and deployment within your team (or even if you are working solo).

setup.py is only needed when you want to distribute your project as a package that can be used by other projects/teams. This could be distributing a library to the world on PyPI or simply packaging up a library that you intend to reuse in other in-house projects.

You would not require a setup.pyfile if your project was an end use-case application that had limited redistribution potential.

