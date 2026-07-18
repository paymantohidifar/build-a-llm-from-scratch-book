# Environment Installation Guide

### 1. Clone the Repository

Clone the repository to your local machine. This command checks out the `main`
branch and places it into a clean `build-a-llm-from-scratch-book` directory:

```bash
git clone https://github.com/paymantohidifar/build-a-llm-from-scratch-book.git --branch main
cd build-a-llm-from-scratch-book/llms-from-scratch

```

This project supports automatic dependency resolution for both **CPU-only** and
**CUDA-enabled** environments across three platforms: **Linux (64-bit)**,
**Windows (64-bit)**, and **macOS (Apple Silicon/ARM64)**.

### 2. Fast Local Installation via `uv`

[uv](https://github.com/astral-sh/uv) is an ultra-fast Python package
installer and resolver.

**For a lightweight CPU-only environment:**

```bash
# Optional: Preview the dependency resolution without installing packages
uv sync --extra cpu --extra dev --dry-run

# Create the virtual environment and install CPU + Dev packages
uv sync --extra cpu --extra dev

# Run the test suite to verify the installation
uv run pytest

# Create the virtual environment and install CPU + Dev packages + Bonus packages
uv sync --extra cpu --extra dev --extra bonus

```

**For a CUDA-enabled (GPU) environment:**

```bash
# Optional: Preview the dependency resolution without installing packages
uv sync --extra gpu --extra dev --dry-run

# Create the virtual environment and install GPU + Dev packages
uv sync --extra gpu --extra dev

# Run the test suite to verify the installation
uv run pytest

# Create the virtual environment and install GPU + Dev packages + Bonus packages
uv sync --extra gpu --extra dev --extra bonus

```

### 3. Local Installation via `pixi` (Isolated Environments)

If you use [Pixi](https://pixi.sh/) for system-level dependency encapsulation,
your packages are managed completely automatically inside a local, hidden `.pixi/` directory.

**For a CPU-only environment:**

```bash
# Optional: Preview the dependency resolution without installing packages
pixi update

# Install the default environment profile (CPU + Dev tools)
pixi install       

# Run the test suite via the built-in Pixi task
pixi run test

# Install the Bonus environment (CPU + Dev tools + Bonus tools)
pixi install -e bonus-cpu-env

```

**For a CUDA-enabled (GPU) environment:**

```bash
# Optional: Preview the dependency resolution without installing packages
pixi update

# Install the dedicated hardware-accelerated environment profile
pixi install -e gpu-env

# Run the test suite inside the GPU environment context
pixi run test

# Install the Bonus environment (GPU + Dev tools + Bonus tools)
pixi install -e bonus-gpu-env

```

### 4. Cloud Notebooks (Google Colab GPU)

To train or evaluate this model using full hardware acceleration on Google Colab,
you must prepare the runtime container first.

> **Required Step:** In the top menu of your Colab notebook, navigate to
**Runtime → Change runtime type**, select **T4 GPU** (or higher), and click **Save**.

Paste and execute the following block in the very first cell of your notebook
to clone the codebase and initialize the high-speed GPU environment:

```python
# Clear any stale directories and clone a fresh copy of the codebase
!rm -rf /content/build-a-llm-from-scratch-book
!git clone https://github.com/paymantohidifar/build-a-llm-from-scratch-book.git --branch main
%cd build-a-llm-from-scratch-book/llms-from-scratch

# Bootstrap uv globally and pull GPU-enabled binaries directly into the system layer
!curl -LsSf https://astral.sh/uv/install.sh | sh && \
export PATH="$HOME/.local/bin:${PATH}" && \
uv pip install -e .[gpu,dev] \
        --system \
        --break-system-packages \
        --color never

# Add `src/` to system path for local imports
import sys
sys.path.append('/content/build-a-llm-from-scratch-book/llms-from-scratch/src')
```

> **Important:** Once the cell finishes running, navigate to **Runtime → Restart session** in the top menu. This clears Colab's background Python cache so it can successfully read the newly installed packages.
