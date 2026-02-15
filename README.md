# TensorFlow Recommenders Environment Guide (WSL2 + uv)

This project is configured for a high-performance Machine Learning environment on Windows 11 (WSL2 Ubuntu) optimized for **Intel 12th Gen i5** hardware using the `uv` package manager. 



---

## 🛠 Setup Instructions

As mentioned, instructions are for **Intel 12th Gen i5** hardware on WSL running Ubuntu 24.04.4 LTS (GNU/Linux 6.6.87.2-microsoft-standard-WSL2 x86_64). Some details might vary on other setups, ask an LLM for specific instructions.

###  Prerequisites

Before cloning, ensure you have the following installed on your WSL2 Ubuntu distribution:

1.  **uv**: New standard Python package manager. Very important here not die of dependency hell.
    ```bash
    curl -LsSf [https://astral.sh/uv/install.sh](https://astral.sh/uv/install.sh) | sh
    ```
2.  **C++ Build Tools**: Required for `ScaNN` and other TFRS extensions.
    ```bash
    sudo apt update && sudo apt install build-essential pkg-config libhdf5-dev -y
    ```


### Setup
1. Clone repo
```bash
git clone ...
```

2. Create Virtual Environment
```bash
uv sync
```
3. (Optional) Add a jupyter kernel to execute notebooks
```bash
uv add --dev ipykernel
uv run ipython kernel install --user --name=tf-recommenders --display-name "Python (TF-Recommenders)"
```
4. (Optional) Enable optimization for Intel CPU/GPU
```bash
export TF_ENABLE_ONEDNN_OPTS=1
```
