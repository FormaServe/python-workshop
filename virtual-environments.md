# Setting Up and Using a Python Virtual Environment on the IBM i

<img src="/images/Logo.png" align="right">

This document provides a step-by-step guide to setting up and using a Python virtual environment on the IBM i, specifically tailored for FormaServe projects.

## Introduction

Virtual environments are a crucial part of Python development, allowing you to create isolated spaces for your projects. This is particularly important when working with multiple projects that may have conflicting dependencies or require different versions of the same package.

## Prerequisites

Ensure Python is installed on your system. You can check by running:

```sh
python3 --version
```

If Python is not installed, you may need to install it using the yum package manager.

## What is a Virtual Environment?

A virtual environment is a self-contained directory that contains a Python installation for a particular version of Python, along with additional packages. It allows you to manage dependencies for different projects separately, avoiding version conflicts.

## Benefits of Using Virtual Environments

- **Dependency Isolation**: Each project can have its own dependencies, regardless of what dependencies every other project has.
- **Version Control**: You can specify which versions of packages your project requires, ensuring consistency across different environments.
- **Easy Management**: You can easily create, activate, and deactivate environments as needed.
- **Portability**: You can share your project dependencies by providing a `requirements.txt` file, rather than including the virtual environment itself in version control.

## Setting Up a Virtual Environment

### Step 1: Install `venv` Module

Most modern Python versions come with the `venv` module by default. You can verify its availability by running:

```sh
python3 -m venv --help
```

If the command is unavailable, install it using:

```sh
yum install python3-venv
```

### Step 2: Create a Virtual Environment

For consistency, FormaServe always uses **.venv** as the name for the virtual environment.

Navigate to your project directory and run:

```sh
python3 -m venv .venv
```

Replace `.venv` with your preferred environment name.

### Step 3: Activate the Virtual Environment

Run the following command to activate your environment:

- On the IFS:
  ```sh
  source .venv/bin/activate
  ```
  ```

Once activated, your terminal prompt should change, indicating you're in the virtual environment.

## Using the Virtual Environment

### Install Dependencies

Use `pip` inside the virtual environment to install packages:

```sh
pip install package_name
```

### List Installed Packages

Check installed packages with:

```sh
pip list
```

### Deactivate the Virtual Environment

Exit the virtual environment by running:

```sh
deactivate
```

## Removing a Virtual Environment

Simply delete the virtual environment folder:

```sh
rm -rf .venv
```
*(On Windows, use `rmdir /s /q .venv` in Command Prompt)*

## Conclusion

Virtual environments are essential for managing dependencies in Python projects. Always activate the relevant environment when working on a project to ensure dependency isolation.

## Authors

* FormaServe Systems Ltd - *All work* - [FormaServe](https://www.formaserve.co.uk)

## Copyright © 2023 FormaServe Systems Ltd

All Rights Reserved. This software is proprietary and confidential. \
Unauthorized copying, modification, distribution, or creation of derivative works of this code is strictly prohibited without the express written consent of FormaServe Systems Ltd.

## Acknowledgments

* **Andy Youens** - *FormaServe Systems Ltd 1990* - All rights reserved.
* **Nick Youens** - *FormaServe Systems Ltd 1990* - All rights reserved.
* **Jane Youens** - *FormaServe Systems Ltd 1990* - All rights reserved.