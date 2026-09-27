\# Factorial CI/CD Python 🚀



This is a simple Python application that calculates the factorial of a number, built to demonstrate Continuous Integration and Continuous Deployment (CI/CD) practices.



\## Features

\* A simple Python `factorial()` function.

\* Automated tests written using `pytest`.

\* A fully automated \*\*GitHub Actions\*\* CI/CD pipeline.



\## The CI/CD Pipeline

Every time code is pushed to the `main` branch, GitHub Actions automatically:

1\. Boots up an Ubuntu Linux server.

2\. Checks out the code.

3\. Installs Python 3.13 and `pytest`.

4\. Runs the automated test suite.

5\. If the tests pass, it packages the source code as a downloadable Artifact!



\## How to run locally

1\. Install the requirements:

&#x20;  ```bash

&#x20;  pip install -r requirements.txt

