# Environment Setup Guide

This project uses [Pixi](https://pixi.sh) for reproducible environment and dependency management.

## Prerequisites

Install Pixi:

```bash
curl -fsSL https://pixi.sh/install.sh | bash
````

Or follow the official installation instructions for your platform:

* [https://pixi.sh/latest/](https://pixi.sh/latest/)

Verify installation:

```bash
pixi --version
```

---

# Clone the Repository

```bash
git clone git@github.com:paymantohidifar/build-a-llm-from-scratch-book.git
cd llms-from-scratch
```

---

# Create the Environment

Install all dependencies and create the default environment:

```bash
pixi install
```

The default environment includes:

* Core dependencies
* Development tools
* Bonus/optional ML tooling

---

# Activate the Environment

```bash
pixi shell
```

---

# Available Environments

## Default Environment

Includes:

* PyTorch
* TensorFlow
* JupyterLab
* Hugging Face ecosystem
* Testing and development tools

Activate with:

```bash
pixi shell
```

## Test Environment

Lightweight environment for testing only:

```bash
pixi shell -e tests
```

---

# Running Common Tasks

## Launch JupyterLab

```bash
pixi run lab
```

## Run Tests

```bash
pixi run test
```

## Install Local Package in Editable Mode

```bash
pixi run install-pkg
```

---

# Key Dependencies

## Core Packages

* Python 3.11
* PyTorch (CPU)
* TensorFlow
* NumPy
* Pandas
* Matplotlib
* JupyterLab
* Tiktoken

## Development Tools

* PyTest
* Build
* Twine
* Safetensors
* Tokenizers

## Bonus ML/NLP Tools

* Transformers
* Hugging Face Hub
* OpenAI SDK
* SentencePiece
* Scikit-learn

---

# Jupyter Kernel Setup

The project includes `pixi-kernel`, allowing the environment to be used directly inside Jupyter.

After activating the environment, start JupyterLab:

```bash
pixi run lab
```

Then select the Pixi kernel from the notebook interface.

---

# Updating Dependencies

To update the lock file and dependencies:

```bash
pixi update
```

---

# Useful Pixi Commands

## List Environments

```bash
pixi info
```

## View Installed Packages

```bash
pixi list
```

## Run Commands Without Activating Shell

```bash
pixi run python
pixi run pytest
```

---

# Platform Support

Current configuration targets:

```toml
platforms = ["linux-64"]
```

Tested primarily on Linux x86_64 systems.

---

# Troubleshooting

## Rebuild Environment

```bash
pixi clean
pixi install
```

## Remove Existing Environment

```bash
pixi clean --all
```

## Verify Python Version

```bash
pixi run python --version
```

Expected output:

```text
Python 3.11.x
```
