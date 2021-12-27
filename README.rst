.. image:: https://img.shields.io/pypi/status/PackageIt
    :alt: PyPI - Status

.. image:: https://img.shields.io/pypi/wheel/PackageIt
    :alt: PyPI - Wheel

.. image:: https://img.shields.io/pypi/pyversions/PackageIt
    :alt: PyPI - Python Version

.. image:: https://img.shields.io/github/v/release/hendrikdutoit/PackageIt
    :alt: GitHub release (latest by date)

.. image:: https://img.shields.io/github/license/hendrikdutoit/PackageIt
    :alt: License

.. image:: https://img.shields.io/github/issues-raw/hendrikdutoit/PackageIt
    :alt: GitHub issues

.. image:: https://img.shields.io/pypi/dm/PackageIt
    :alt: PyPI - Downloads

.. image:: https://img.shields.io/github/search/hendrikdutoit/PackageIt/GitHub
    :alt: GitHub Searches

.. image:: https://img.shields.io/codecov/c/gh/hendrikdutoit/PackageIt
    :alt: CodeCov
    :target: https://app.codecov.io/gh/hendrikdutoit/PackageIt

.. image:: https://img.shields.io/github/workflow/status/hendrikdutoit/PackageIt/Pre-Commit
    :alt: GitHub Actions - Pre-Commit
    :target: https://github.com/hendrikdutoit/PackageIt/actions/workflows/pre-commit.yaml

.. image:: https://img.shields.io/github/workflow/status/hendrikdutoit/PackageIt/CI
    :alt: GitHub Actions - CI
    :target: https://github.com/hendrikdutoit/PackageIt/actions/workflows/ci.yaml

.. image:: https://img.shields.io/pypi/v/PackageIt
    :alt: PyPi

Framework for managing the scaffolding for new and existing Python Packages.

    Use a configuration (.ini) file to: 1. Create the "scaffolding" for a new package. 2. Examine existing scaffolding and add missing components like directories and files. 3. Version control 4. Apply PEP8 via Black 5. Update Git and GitHub 6. Upload to PyPi 7. PEP12 doc strings 8. Create a virtual environment for the project 9. Special thanks to Jacob Tomlinson. This application is based on his article `Creating an open source Python project from scratch <https://jacobtomlinson.dev/series/creating-an-open-source-python-project-from-scratch/>`_. 10. Configurations through templates which are easier to change. 11. Step-by-step procedure for beginners as well as connoisseurs. Intention was educational, but also functional. This is a starting block to create the initial structure that can be used to grow it bigger. ToDo 1. Silence the scripting implementations and write output to log file. 2. Write the number of tests and time to the ini and then add it to the readme.rst 3. Warning in documentation about Dropbox grabbing files 4. Upfront tasks 4.1 Create the following accounts - Github - ReadTheDocs https://docs.readthedocs.io/en/stable/tutorial/ - CodeCov 5. Discuss the usage of templates i.e. where the default templates are and how to use a custom template. 6. Rename all the templates and read the template name from the pimt.ini 7. Read the module | package setting from the commandline rather than the ini file. Reading it from the ini forces the creation off 2 ini files, one for packages and the other for modules 8. Check if it is necessary for the pre-commit onto run before CI process on GitHUb and fix if necessary. Documentation 1. Tokens - GitHUb - ReadTheDocs 2. Runs the system without human intervention i.e. a GUI interface. No GUI, questions. All through setting up the ini and templates. - Templates gives opportunity to add own requirements and changes. - Changes in (version) applications using the templates can also be more easily accommodated. - User can configure his/her own templates and leave the defaults intact. 3. You cannot delete a project on ReadTheDOcs via API. To properly run the tests the TestProject you are creating must be deleted manually on ReadTheDocs 4. PackageIt must tun in a virtual environment 5. All packages and modules created by PackageIt must run in a virtual environment. Conventions 1. Release note title name = "Ver n.n.n" 2. Release tag name = "Tag n.n.n' 3. GitHub enhancement branch name = "Enhancement_nnnn" where nnnn is the GitHub issue number with leading zeros. 4. Color Coding - Yellow is informational i.e. contents of batch fields - Purple is is mile stone messages - White is messages by 3rd party API's - Red - Warning or error messages

=======
Testing
=======

This project uses ``pytest`` to run tests and also to test docstring examples.

Install the test dependencies.

.. code-block:: bash

    $ pip install -r requirements_test.txt

Run the tests.

.. code-block:: bash

    $ pytest tests
    === XXX passed in SSS seconds ===

==========
Developing
==========

This project uses ``black`` to format code and ``flake8`` for linting. We also support ``pre-commit`` to ensure these have been run. To configure your local environment please install these development dependencies and set up the commit hooks.

.. code-block:: bash

    $ pip install black flake8 pre-commit
    $ pre-commit install

=========
Releasing
=========

Releases are published automatically when a tag is pushed to GitHub.

.. code-block:: bash

    # Set next version number
    export RELEASE = x.x.x
    
    # Create tags
    git commit --allow -empty -m "Release $RELEASE"
    git tag -a $RELEASE -m "Version $RELEASE"
    
    # Push
    git push upstream --tags
