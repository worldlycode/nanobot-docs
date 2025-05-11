# Switching to uv for Package and Environment Management

**Date:** May 11, 2025  
**Author:** sam-i-am

<pre style="color: #3f51b5; font-size: 1.1rem;"><code>"Hello World! 🌐"</code></pre>


Using pip as a package manager together with venv to manage isolated python environments has historically been the default way to manage packages and local environments.  However, there are a few drawbacks. It is slow for installing large packages, and the requirements files include all of the sub-dependencies of each package.  

As a best practice it is ideal to have only the high-level packages in the installation, and to let those packages manage the installation of the sub-dependencies.  

[uv](https://docs.astral.sh/uv/) is now gaining popularity as a package and environemnt manager, combinding the functions of both pip and venv. I am jumping on the bandwagon, especially after waiting over 5 minutes for the `docling` installation which includes pytorch and hugging face models.  The same installation only takes seconds with uv.  

## venv:
- Creates isolated Python environments with their own packages
- Doesn't install packages itself
- Included in Python's standard library since 3.3

## pip:
- The standard Python package manager
- Installs, upgrades, and manages Python packages
- Used within virtual environments created by venv

## uv is a newer alternative that combines both functions:
- Much faster package installer than pip (written in Rust)
- Also creates virtual environments like venv
- Often 10-100x faster than pip for installation operations
- Maintains compatibility with pip's ecosystem (requirements.txt, etc.)

## Installation of uv

I followed the [blog post by Dave Ebbelaar](https://daveebbelaar.com/blog/2024/03/20/getting-started-with-uv-the-ultra-fast-python-package-manager/) to set up uv on my WSL2 linux environment on windows.  

on macOS (using Homebrew)
```bash
brew install uv
```

On Linux / macOS / WSL (using curl)
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

On Windows (using PowerShell)
```bash
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

## Creating a virtual environment using uv

run the following command
```bash
uv venv
```

This will create a folder named `.venv`.  To switch to this environment

```bash
source .venv/bin/activate 
```

On Windows this would be:
```bash
.venv\Scripts\activate
```

If you now type:
```bash
which python
```

You will be able to verify that you are now working in the local .venv environment.

## Building the `pyproject.toml` file

The requirements that a project needs are kept in a `.toml` file in the root directoy with the name `pyproject.toml`  

Below is an example of such a file for an example `nanobot` project.  There are many other things that can be included in this file, but these are the basics.

```toml
[project]
name = "nanobot"
version = "0.1.0"
description = "NanoBot - AI assistant application"
requires-python = ">=3.10"
dependencies = [
    # Database
    "psycopg2-binary",
    
    # Configuration
    "pydantic-settings",
    "python-dotenv",
    
    # Template Engine
    "jinja2",
    
    # Logging
    "logfire",
    
    # Data Processing
    "pandas",
    "matplotlib",
    
    # Document Processing
    "docling",
    "docling-core",
    
    # OpenAI
    "openai",
    
    # Tokenization
    "tiktoken",
    
    # Web UI
    "streamlit",
]
```

## Installing using Sync

To install the dependencies in the `pyproject.toml` file, you will run the following command:

```bash
uv sync
```

You will then see the packages and their dependencies being installed, ofter at a speed of 10x-100x of what a standard pip installation would take. 

## Addidng packages with uv

You will preceed many of your commands with `uv`.  ie for package installation:

```bash
uv add [package name(s)]
```

## uv lock

This will allow you to lock the dependencies and versions.  Please look into the [uv docs](https://docs.astral.sh/uv/) for more information. 


