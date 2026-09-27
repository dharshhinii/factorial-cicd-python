# Factorial CI/CD (Python)

A lightweight Python application that calculates the factorial of a number, configured with automated testing and a Continuous Integration (CI) pipeline using GitHub Actions.

## Overview

This repository demonstrates modern software engineering and DevOps practices for a Python codebase. It includes input-validated arithmetic logic, unit testing with `pytest`, and automated CI/CD workflows that test and package the source code on every push.

## Project Structure

```text
factorial-cicd-python/
|-- .github/
|   `-- workflows/
|       `-- ci.yml              # GitHub Actions CI workflow definition
|-- factorial.py                # Factorial function implementation
|-- test_factorial.py           # Unit tests using pytest
|-- requirements.txt            # Project dependencies
`-- README.md                   # Project documentation
```

## Features

- **Factorial Implementation**: Computes factorials iteratively with error handling for negative integers (`ValueError`).
- **Automated Testing**: Unit test suite using `pytest` covering base cases, positive integers, and invalid inputs.
- **Continuous Integration**: GitHub Actions workflow running on Python 3.13 and Ubuntu to test and package build artifacts.

## Getting Started

### Prerequisites

- Python 3.10 or higher (Python 3.13 recommended)
- `pip` package manager
- `git`

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/dharshhinii/factorial-cicd-python.git
   cd factorial-cicd-python
   ```

2. (Optional) Create and activate a virtual environment:
   - On Windows (PowerShell):
     ```powershell
     python -m venv venv
     .\venv\Scripts\Activate.ps1
     ```
   - On Linux/macOS:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```

3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Import and use the `factorial` function in Python:

```python
from factorial import factorial

# Example usage
print(factorial(0))   # Returns 1
print(factorial(5))   # Returns 120
print(factorial(10))  # Returns 3628800
```

Run directly from the command line:

```bash
python -c "from factorial import factorial; print(factorial(5))"
```

## Running Tests

Run the test suite using `pytest`:

```bash
pytest
```

Run with verbose test output:

```bash
pytest -v
```

## CI/CD Pipeline

The GitHub Actions workflow is defined in [`.github/workflows/ci.yml`](.github/workflows/ci.yml).

On every push to the `main` branch, the pipeline executes the following steps:

1. **Checkout**: Checks out the repository code.
2. **Environment Setup**: Configures Python 3.13 on an `ubuntu-latest` runner.
3. **Dependency Installation**: Installs packages specified in `requirements.txt`.
4. **Test Execution**: Executes `pytest` to verify all test cases pass.
5. **Artifact Packaging**: Prepares source files (`factorial.py`, `test_factorial.py`, `requirements.txt`) in a `dist/` directory.
6. **Artifact Upload**: Publishes the build bundle as `factorial-python` via `actions/upload-artifact@v4`.
