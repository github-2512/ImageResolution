# EffiSR-Net: A Comparative Analysis of Image Super-Resolution Models

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](h[ttps://colab.research.google.com/github/github-2512/ImageResolution/blob/main/ImageResolution.ipynb](https://colab.research.google.com/drive/1ygy1ZC90mm5iPHFWU7lRY6rxKa4bmqLc?usp=sharing))

This repository contains the code and results for a comparative study of Single Image Super-Resolution (SISR) models. It evaluates our proposed model, **EffiSR-Net**, against state-of-the-art models like **ESRGAN** and **SwinIR** on the standard **Set5** benchmark dataset.

The entire evaluation is contained within a Google Colab notebook for easy setup and reproducibility.

---

## 📊 Results

### Quantitative Comparison

The models were evaluated on the Set5 dataset based on PSNR (Peak Signal-to-Noise Ratio), SSIM (Structural Similarity Index), and inference latency. Our model, EffiSR-Net, achieves a competitive balance between performance and efficiency.

![Results Table](results_table.png)

### Visual Comparison

Here is a qualitative comparison on the `head.png` image from the Set5 dataset, showing the output from each model against the ground truth.

![Visual Comparison](visual_comparison_head.png)

---

## ✨ Key Features

* **Model Comparison**: Benchmarks our proposed lightweight **EffiSR-Net** against **ESRGAN** and **SwinIR**.
* **Comprehensive Evaluation**: Uses standard SISR metrics including **PSNR**, **SSIM**, and **Latency**.
* **Reproducible Environment**: A single Google Colab notebook (`.ipynb`) handles all dependencies, setup, and evaluation.
* **Built on BasicSR**: Utilizes the powerful and popular [BasicSR](https://github.com/XPixelGroup/BasicSR) framework for PyTorch.

---

## 🚀 Getting Started

To reproduce these results, follow these steps.

### Prerequisites

1.  **Google Account**: To use Google Colab and Google Drive.
2.  **Required Files**: You need the pre-trained model weights and the dataset.

### Setup Instructions

1.  **Clone the Repository (Optional)**:
    You can clone this repository to have a local copy of the code.

    ```bash
    git clone [https://github.com/github-2512/ImageResolution.git](https://github.com/github-2512/ImageResolution.git)
    ```

2.  **Prepare Google Drive**:
    The Colab notebook is configured to read files from a specific folder in your Google Drive.
    * In your Google Drive, go to `My Drive` and create a folder named `SR_Project`.
    * Download the following files and place them inside the `SR_Project` folder:
        * **Models**:
            * [**ESRGAN Model**](https://github.com/XPixelGroup/BasicSR/releases/download/v1.3.4/ESRGAN_SRx4_DF2KOST_official-998c3655.pth) (Right-click and "Save Link As...")
            * [**SwinIR Model**](https://github.com/JingyunLiang/SwinIR/releases/download/v0.0/001_classicalSR_DF2K_s64w8_SwinIR-M_x4.pth) (Right-click and "Save Link As...")
        * **Dataset**:
            * Download and unzip the [**Set5 Dataset**](http://vllab.ucmerced.edu/wlai24/LapSRN/results/SR_testing_datasets/Set5.zip). Place the `Set5` folder inside `SR_Project`.

    Your final folder structure in Google Drive should look like this:

    ```
    My Drive/
    └── SR_Project/
        ├── ESRGAN_SRx4_DF2KOST_official-998c3655.pth
        ├── 001_classicalSR_DF2K_s64w8_SwinIR-M_x4.pth
        └── Set5/
            ├── baby.png
            ├── bird.png
            └── ...
    ```

### How to Run

1.  **Open in Colab**: Click the "Open in Colab" badge at the top of this page or manually open the `.ipynb` file in [Google Colab](https://colab.research.google.com/).
2.  **Mount Google Drive**: Run the first code cell. It will prompt you to authorize and mount your Google Drive.
3.  **Run the Notebook**: Go to the menu and click **Runtime -> Run all**. The script will:
    * Set up the BasicSR environment.
    * Verify that all required models and dataset files exist in your Drive.
    * Run the evaluation for each model.
    * Generate and display the final comparison table and visual figures.

---

## 🛠️ Models Used

* **EffiSR-Net (Ours)**: A lightweight version of ESRGAN's architecture (RRDBNet) with only 10 residual blocks instead of 23. This significantly reduces the parameter count (`7.35M`) while maintaining strong performance.
* **ESRGAN**: The official Enhanced Super-Resolution Generative Adversarial Network model with 23 residual blocks (`16.70M` parameters).
* **SwinIR**: A state-of-the-art image restoration model based on Swin Transformers (`11.90M` parameters).

## Acknowledgments

* This project is built upon the excellent [BasicSR (mmsr)](https://github.com/XPixelGroup/BasicSR) framework.
* Thanks to the original authors of [ESRGAN](https://github.com/xinntao/ESRGAN) and [SwinIR](https://github.com/JingyunLiang/SwinIR) for their foundational work and for making their models publicly available.
