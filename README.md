

This README explains what the code does, how to use it, and what results to expect.

# 🖼️ Gaussian Noise Denoising Comparison in MATLAB

This script provides a comparative analysis of two popular image denoising methods—a **Traditional Adaptive Filter (Wiener Filter)** and an **AI-based Deep Learning Filter (DnCNN)**—applied to a grayscale image corrupted by Additive White Gaussian Noise (AWGN).

The comparison is conducted both **visually** (by displaying the filtered images) and **quantitatively** (using PSNR and SSIM metrics).

-----

## 🚀 Prerequisites

To run this script, you must have the following MATLAB toolboxes installed:

  * **Image Processing Toolbox™** (for `im2double`, `imnoise`, `wiener2`, `psnr`, `ssim`)
  * **Deep Learning Toolbox™** (for `denoisingNetwork`, `denoiseImage`)

-----

## 🛠️ Setup and Execution

1.  **Save the Script:** Save the provided MATLAB code as a `.m` file (e.g., `denoising_comparison.m`).

2.  **Image File:** Ensure the image file `'cameraman.tif'` (a standard example image included with MATLAB) is in the same directory as the script, or replace it with the path to your desired grayscale image.

3.  **Run:** Execute the script in the MATLAB Command Window:

    ```matlab
    denoising_comparison
    ```

### Key Parameters

You can easily adjust the severity of the noise by changing the `noiseSigma` variable in **Section 1**:

| Variable | Description | Default Value |
| :--- | :--- | :--- |
| `noiseSigma` | Standard deviation of the Gaussian noise, expressed in the range $[0, 1]$ (for double precision images). | `0.04` |

-----

## 📊 Comparison Summary

The script generates a figure and prints metrics to the Command Window, demonstrating the performance differences:

### 1\. Visual Comparison

A figure window titled **"Gaussian Noise Denoising Comparison"** will appear with four subplots:

1.  **Original Image:** The clean source image.
2.  **Noisy Image:** The image corrupted by AWGN.
3.  **Traditional (Wiener) Filter:** The output of the `wiener2` filter. This often provides good overall smoothing but can blur fine details.
4.  **AI (DnCNN) Filter:** The output of the pre-trained Deep Neural Network (DnCNN). This typically achieves superior noise reduction while better preserving complex textures and edges.

### 2\. Quantitative Results

The Command Window will display a table comparing the quality metrics:

| Metric | Description | Goal |
| :--- | :--- | :--- |
| **PSNR (dB)** | **Peak Signal-to-Noise Ratio.** Measures the ratio between the maximum possible power of a signal and the power of corrupting noise. | **Higher is better.** |
| **SSIM** | **Structural Similarity Index.** Measures the perceived change in structural information (texture, edges) between the noisy/filtered image and the original. | **Closer to 1 is better.** |

The **AI (DnCNN) Filter** is expected to yield the highest PSNR and SSIM values, confirming its superior performance for this specific type of noise.

```text
--- Image Quality Metrics Comparison ---
Method | PSNR (dB) | SSIM
----------------------|-----------|----------
Noisy Image | XX.XX | X.XXXX
Traditional (Wiener) | XX.XX | X.XXXX
AI (DnCNN) | XX.XX | X.XXXX
```
