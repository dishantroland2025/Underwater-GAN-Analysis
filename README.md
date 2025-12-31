# Underwater GAN Analysis

**Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency**

---

## Overview

This repository provides the **official implementation and experimental code** accompanying the manuscript:

> **“Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency”**
> *Submitted to* **The Visual Computer (Springer Nature)**

The goal of this work is to conduct a **systematic and reproducible comparison** of two representative GAN-based underwater image enhancement models:

* **Sea-Pix-GAN** – a wide U-Net–based architecture emphasizing structural fidelity
* **MuLA-GAN** – a lightweight attention-driven architecture optimized for efficiency

Underwater images suffer from severe degradation due to **light absorption, wavelength-dependent attenuation, and scattering**. These effects reduce contrast, distort color balance, and obscure structural details, negatively impacting downstream tasks such as marine monitoring and autonomous navigation.

This repository enables researchers to **reproduce all reported experiments**, evaluate quantitative metrics, and inspect qualitative results across multiple benchmark datasets.

---

## Models Included

### 1. Sea-Pix-GAN

* Wide U-Net generator
* High-weight L1 loss
* Focus on perceptual and structural fidelity
* Higher computational cost

### 2. MuLA-GAN

* Narrow attention-based U-Net
* VGG-based perceptual loss
* Optimized for inference efficiency
* Reduced memory and runtime requirements
* 
---

## Datasets

Experiments are conducted on the following **public benchmark datasets**:

* **UIEB**
* **LSUI**
* **UFO-120**
* **GoPro-Underwater**

Only the **paired data** are required for training where applicable.

---

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/dishantroland2025/Underwater-GAN-Analysis.git
cd Underwater-GAN-Analysis
```

### 2. Environment setup

We recommend using **Conda**.

```bash
conda create -n underwater_gan python=3.8
conda activate underwater_gan
```

Install dependencies:

```bash
pip install torch torchvision numpy opencv-python scikit-image matplotlib tqdm
```

GPU acceleration requires:

* CUDA ≥ 11.x
* Compatible PyTorch build

---

## Running Experiments

All experiments are provided as Jupyter notebooks and can be run locally or on Google Colab.

Example:

```bash
jupyter notebook "sea-pix-GAN on UFO-120.ipynb"
```

Follow the instructions inside each notebook to:

* Set dataset paths
* Load pretrained weights (if applicable)
* Run inference and evaluation

---

## Evaluation Metrics

The following metrics are used, consistent with the manuscript:

* **PSNR** – Peak Signal-to-Noise Ratio
* **SSIM** – Structural Similarity Index
* **UIQM** – Underwater Image Quality Measure

Speed and efficiency are measured via:

* Inference time per image
* Parameter count
* Memory footprint

---

## Reproducibility Notes

* All hyperparameters match those reported in the paper.
* Random seeds are fixed where applicable.
* Metric implementations are consistent across models.
* Hardware details are specified in the manuscript.

---


## License

This project is released under the **Apache 2.0 License**.
See the `LICENSE` file for details.

---

## 📄 Manuscript & Citation

This codebase is directly associated with:

> Singh, R. *et al.* (2025). Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency. *Submitted to The Visual Computer*.

If you use this repository, please cite:
```bibtex

```
---

## Contact

For questions regarding the code or experiments:

Email: *dishantroland@gmail.com*

---

