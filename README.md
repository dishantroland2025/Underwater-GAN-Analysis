# Underwater GAN Analysis
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18134086.svg)](https://doi.org/10.5281/zenodo.18134086)

**Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency**

> [!IMPORTANT]
> **Manuscript Association & Citation:** This repository provides the official implementation and reproducibility artifacts for the manuscript: 
> **“Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency”** > *Currently under review at **The Visual Computer (Springer Nature)***. 
> 
> If you find this research or code useful, we kindly urge you to cite the associated manuscript as detailed in the [Manuscript & Citation](#-manuscript--citation) section below.

---

## Overview

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
---

## Datasets

Experiments are conducted on the following **public benchmark datasets**:

* **UIEB**
* **LSUI**
* **UFO-120**
* **GoPro**

Only the **paired data** are required for training where applicable.

---

## Performance Benchmarks (Verified on Tesla T4)

The following metrics represent native performance on standard hardware. Sea-Pix-GAN demonstrates superior throughput despite higher complexity due to optimized kernel execution.

| Model | Parameters (M) ↓ | GFLOPS ↓ | Latency (ms) ↓ | Throughput (FPS) ↑ |
|---|---|---|---|---|
| Sea-Pix-GAN | 54.42 | 18.20 | 7.15 | 139.95 |
| MuLA-GAN | 16.56 | 13.10 | 9.46 | 105.67 |

---

## Repository Structure

The repository is organized into two main sections to separate the raw research phase from the final validated results:

* **`reproducible_code/`**: Contains the primary notebooks designed for peer review. These scripts feature a centralized path configuration for easy testing on any dataset.
* **`original_experiments/`**: Contains the full suite of training and testing notebooks used across all four datasets (UIEB, LSUI, UFO-120, GoPro).

---

## Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/dishantroland2025/Underwater-GAN-Analysis.git
cd Underwater-GAN-Analysis
```

### 2. Environment setup
Install the core requirements:
```bash
pip install torch torchvision numpy opencv-python scikit-image matplotlib ptflops pyyaml
```

---

## Reproducing Results

For reviewers and researchers, we recommend starting with the Reproducible Notebooks. These are designed to be executable after setting your local dataset paths.

1. Navigate to the `reproducible_code/` directory.
2. Open `sea-pix-GAN_reproducible.ipynb` or `MuLA-GAN_reproducible.ipynb`.
3. Set your `BASE_PATH` to point to your local version of the UIEB, LSUI, or custom dataset.
4. Run all cells to verify Training, Testing, and Quantitative Evaluation (SSIM, PSNR, UIQM).

---

## Quantitative Results Summary

Our analysis shows that Sea-Pix-GAN provides superior structural preservation and perceptual quality:

* **SSIM**: 16.33% higher average than MuLA-GAN (0.9534 vs 0.8196).
* **UIQM**: 61.89% higher average perceptual score (4.83 vs 2.98).
* **Efficiency**: Achieves real-time performance at 139.95 FPS with 7.15 ms latency on Tesla T4 hardware, suitable for modern autonomous underwater vehicles (AUVs).

---

## Sample Images

<p align="center">
  <img src="Sample_Images.png" width="95%" alt="Sample images from LSUI, UFO-120, UIEB, and GoPro datasets">
</p>

<p align="center">
  <em>
  Figure: Sample images from the four datasets used in this study:
  (a) LSUI, (b) UFO-120, (c) UIEB, and (d) GoPro.
  </em>
</p>

The figure illustrates the diversity of visual characteristics across datasets, including
color degradation, haze, scattering, low contrast, and motion blur.  
These datasets collectively enable a comprehensive evaluation of underwater image
enhancement and restoration performance under varied real-world conditions.

---

## Reproducibility Notes

* All hyperparameters match those reported in the paper.
* Metric implementations are consistent across models.
* Hardware details are specified in the manuscript.

---


## License

This project is released under the **Apache 2.0 License**.
See the `LICENSE` file for details.

---

## Manuscript & Citation

This codebase is directly associated with:

> Singh, R. *et al.* (2025). Comparative Analysis of GAN Architectures for Enhanced Underwater Image Quality and Efficiency. *Submitted to The Visual Computer*.

If you use this repository, please cite:
```bibtex
@article{pradhan2026underwater,
  title={Comparative Analysis of {GAN} Architectures for Enhanced Underwater Image Quality and Efficiency},
  author={Pradhan, Ashis and Das, Dishant and Singh, Roland},
  journal={The Visual Computer},
  year={2026},
  note={Under Review. Code and artifacts available at: https://doi.org/10.5281/zenodo.18134086},
  url={https://github.com/dishantroland2025/Underwater-GAN-Analysis},
}
```
---

## Contact

For questions regarding the code or experiments:

Email: *dishantroland@gmail.com*

---

