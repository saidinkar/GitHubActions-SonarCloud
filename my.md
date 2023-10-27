#QA Suite

[![Python QA suite](https://github.com/archinsurance/aigi-actpy-python-platform/actions/workflows/QAsuite.yml/badge.svg?branch=main)](https://github.com/archinsurance/aigi-actpy-python-platform/actions/workflows/QAsuite.yml)

This github actions workflow is designed to ensure code quality and consistency by performing linting, code formatting, pytest and static code analysis. This workflow is triggered automatically when you open a pull request to the main branch.
In the environment field of the workflow we have two variables i.e. 

`PYTHON_VERSION` - where you can mention your python version you want to use.
`SRC_DIRECTORY` - Here you can mention your source code path.

In this workflow there are multiple step -
##1. Checkout repository:
   
   In this step the workflow fetches the latest code from the repository.
   
##2. Set up Python version:
   
   In this step it configures the python environment based on the specified version mentioned in env variable `PYTHON_VERSION`.
   
##3. Install python dependancies:
   
   In this step it will install all the required project dependencies from `requirements.txt` file and other dependencies which will required for our workflow.

##4. Linting
   
   In this step it checks your code for style and quality issues using Flake8 and Pylint.

-   Flake8: Capable of detecting both logical and stylistic lint. It adds the style and complexity checks of pycodestyle to the logical lint detection of PyFlakes.
-   Pylint: Pylint is a linting tool that not only checks for coding style violations but also looks for programming errors, potential bugs, and offers code quality improvements. It rates code quality with a numerical score.

##5. Code Formatting:
    
   In this step the Code formatters helps you format source code automatically. The main purpose of code formatters is to standardize the formatting of code across a project, making it easier to read and understand code. Here we are using Isort and black for code formatting.

-   Isort: Isort is a utility that automatically sorts and organizes import statements within Python code, ensuring a consistent import order and improving code readability.
-   Black: Black is a Python code formatter that reformats code to follow the Black code style. It enforces a strict, opinionated formatting style that eliminates formatting-related debates and maintains a consistent codebase.
   
   
##6. Pytest:
   In this step it will perform unit testing using pytest and the pytest framework makes it easy to write small, readable tests, and can scale to support complex functional testing for applications and libraries.
   You can create a new file called `test_app.py`, under the test folder containing a function, and a test. pytest discovers all tests following its Conventions for Python test discovery, so it finds both `test_prefixed functions`. There is no need to subclass anything, but make sure to prefix your class with Test otherwise the class will be skipped. 

   
##7. Static Code Analysis:
   In this step it will perfrom static code analysis using SonarCloud which provides detailed analysis across multiple dimensions of the code. These are helpful in identifying common mistakes made by developers and ensure that the code is of high quality. SonarCloud will also give an indicator of how much time is required to fix all the reported issues and remove the technical issues.

-   You can find the SonarCloud code analysis in SonarCloud portal https://sonarcloud.io/organizations/archinsurance/projects
-   You need to login with your GitHub credentials and you can search for your project in order to check information about it. The project name would be same as the name of the GitHub repository.
-   Here you can find all the branches (e.g. main or feature/*) and you can also find the analysis of all the pull requests raised in GitHub.
-   You need to check that your code meets all the metrics that informs you whether your code meets minimum level of quality required for the project i.e.
        -	Coverage is less than 80.0%
        -	Duplicated Lines is greater than 3.0%
        -	Maintainability Rating is worse than A
        -	Reliability Rating is worse than A
        -	Security Hotspots Reviewed is less than 100%

   By following these steps, you can ensure that youe code adheres to the coding standards and passes quality checks before merging into main branch.

   


