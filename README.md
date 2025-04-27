# Prostate‑Cancer‑Treatment‑Prediction

> **Machine‑learning pipeline and EDA for predicting prostate‑cancer treatment decisions.**  
> This README explains how to reproduce the environment with **[Astral uv](https://astral.sh/docs/uv)**, register the Jupyter kernel, and run the notebooks or scripts.

---

## 1  Prerequisites

| Tool | Min version | Notes |
|------|-------------|-------|
| **Python 3.12.x** | 3.12.0 | TensorFlow currently ships wheels only for 3.9 → 3.12. |
| **Homebrew** (macOS) | — | Easiest way to install extra Python versions. |
| **VS Code** + *Jupyter* & *Python* extensions | — | Comfortable, but any Jupyter client works. |

---

## 2  Cloning and pinning Python 3.12

```bash
# Clone the repository
$ git clone https://github.com/diogoalmd/prostate-cancer-treatment-prediction.git
$ cd prostate-cancer-treatment-prediction

# (A) Let uv download its own CPython‑3.12 build
$ uv venv --python 3.12           # creates .venv in ./.venv

# (B) …or use Homebrew’s Python 3.12 if you prefer it system‑wide
$ brew install python@3.12        # once
$ uv venv --python $(brew --prefix)/opt/python@3.12/bin/python3.12

---

## 3 Activating the environment & installing dependencies

$ source .venv/bin/activate

# All core libs, including TensorFlow, EDA, and Jupyter support
$ uv add pandas numpy matplotlib seaborn scikit-learn imbalanced-learn \
         xgboost tensorflow ydata-profiling ipykernel jupyter

$ uv add my-new-lib another-lib
---

## 4 Registering the Jupyter kernel (once per machine)

$ python -m ipykernel install --user \
      --name prostate-cancer-treatment-prediction \
      --display-name "Prostate Cancer (uv)"

---