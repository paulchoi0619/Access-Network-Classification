# Access-Network-Classification


A notebook-based machine learning project for **access network classification**.

This repository benchmarks multiple model families for a multi-class classification task, including:

- **k-Nearest Neighbors (kNN)**
- **XGBoost**
- **Transformer-based models**
  - default configuration
  - small variant
  - medium variant

The experiments are organized as separate Jupyter notebooks and appear to be evaluated across **5 runs / seeds** for more stable comparison.

---

## Repository Structure

```text
Access-Network-Classification/
├── 5rounds_default_config_transformer.ipynb
├── 5rounds_knn_20.ipynb
├── 5rounds_medium_transformer.ipynb
├── 5rounds_small_transformer-Copy1.ipynb
├── 5rounds_xgboost.ipynb
└── README.md
```

---

## Project Goal

The goal of this project is to compare different machine learning approaches for classifying access-network data and measure their performance using:

- Accuracy
- Macro F1
- Weighted F1
- Precision / Recall
- Confusion matrices
- Training time
- Inference time

The repository is currently notebook-centric, making it suitable for experimentation, benchmarking, and model comparison.

---

## Models Evaluated

### 1. kNN
The kNN notebook uses a nearest-neighbor pipeline with preprocessing and repeated evaluation over 5 runs.

### 2. XGBoost
The XGBoost notebook evaluates a gradient-boosted tree baseline and reports strong test performance with repeated runs.

### 3. Transformers
The repository also includes multiple Transformer experiment notebooks with different model sizes/configurations.

---

## Reported Results

| Model | Test Accuracy | Test Macro F1 | Notes |
|------|---------------:|--------------:|------|
| kNN | 0.5833 | 0.5746 | Simple baseline |
| XGBoost | 0.8132 | 0.7999 | Strongest performance |
| Default Transformer | 0.4783 | 0.3827 | Higher training/inference cost in shown run |

> These values are the mean results reported across 5 runs in the notebooks currently available in the repo.

---

## Findings

- **XGBoost** performs best.
- **kNN** provides a simple baseline for comparison.
- The **Transformer** results underperform the classical baselines in the default configuration.

This suggests that, for the current dataset/setup, classical tabular methods may be more effective than the tested Transformer configuration.

---

## Requirements

Because this project is notebook-based, dependencies are inferred from the experiment files. You will likely need a Python environment with packages such as:

```bash
pip install numpy pandas scikit-learn jupyter matplotlib xgboost torch faiss-cpu
```

Depending on your environment and notebook configuration, you may also want:

```bash
pip install notebook jupyterlab
```

If you have GPU support for FAISS or PyTorch, you can install the appropriate CUDA-enabled versions instead.

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/paulchoi0619/Access-Network-Classification.git
cd Access-Network-Classification
```

2. Install dependencies.

3. Launch Jupyter:

```bash
jupyter notebook
```

4. Open any notebook, for example:

- `5rounds_knn_20.ipynb`
- `5rounds_xgboost.ipynb`
- `5rounds_default_config_transformer.ipynb`

5. Run the cells from top to bottom.

---

## Data

The data is found in the **Releases** section.

