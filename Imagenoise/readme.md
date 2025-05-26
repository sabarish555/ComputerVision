# Image Noise and Denoising using Gaussian Noise

This project explores the impact of **Gaussian noise** on images and demonstrates techniques to denoise them using image processing filters. The objective is to understand noise modeling, visualize the effects, and apply denoising techniques effectively.

---

## 📌 Project Objectives

- Add **Gaussian noise** to images with controlled parameters.
- Visualize the effect of noise on image quality.
- Apply denoising filters such as **Gaussian Blur**, **Median Filter**, and **Bilateral Filter**.
- Measure and compare denoising performance using **PSNR** and **SSIM** metrics.

---

## 🧪 Technical Overview

### 1. Gaussian Noise Model

Gaussian noise is a type of statistical noise having a probability density function (PDF) equal to that of the **normal distribution** (a.k.a. Gaussian distribution):

P(x) = (1 / √(2πσ²)) × exp(−(x − μ)² / (2σ²))

Where:

P(x) is the probability of the noise value x
μ is the mean of the distribution (commonly 0 for Gaussian noise)
σ is the standard deviation (controls how much noise is added)
exp denotes the exponential function

In this project, Gaussian noise is added pixel-wise:

I_noisy(x, y) = I(x, y) + N(0, σ²)




Clipping is applied to keep pixel values in [0, 255].

---

### 2. Denoising Filters

#### 🔹 Gaussian Blur
Applies a Gaussian kernel to smooth the image, reducing high-frequency noise.

G(x, y) = (1 / (2πσ²)) * exp(-(x² + y²) / (2σ²))



Used with `cv2.GaussianBlur`.

#### 🔹 Median Filter
Replaces each pixel with the median of its neighborhood. Very effective against **salt-and-pepper** and **impulse** noise.

Used with `cv2.medianBlur`.

#### 🔹 Bilateral Filter
Preserves edges while reducing noise. Combines domain and range filtering:

I_filtered(p) = (1 / W_p) * Σ_{q ∈ Ω} I(q) * f_s(||p - q||) * f_r(|I(p) - I(q)|)


Used with `cv2.bilateralFilter`.

---

## 📊 Evaluation Metrics

### 1. PSNR (Peak Signal-to-Noise Ratio)

PSNR = 10 * log10(MAX_I² / MSE)

Where:
- `MAX_I` = 255 for 8-bit images,
- `MSE` = Mean Squared Error between original and denoised image.



Higher PSNR = better quality.

---

### 2. SSIM (Structural Similarity Index)

Measures perceptual similarity between images.

SSIM(x, y) = [(2μ_xμ_y + C₁)(2σ_xy + C₂)] / [(μ_x² + μ_y² + C₁)(σ_x² + σ_y² + C₂)]


Where:
- `μ_x`, `μ_y` are mean intensities,
- `σ_x`, `σ_y` are variances,
- `σ_xy` is the covariance,
- `C₁`, `C₂` are constants to stabilize division.

---

## 🖼️ Sample Results

| Method         | PSNR ↑ | SSIM ↑ |
|----------------|--------|--------|
| Noisy          | 20.5   | 0.71   |
| Gaussian Blur  | 23.7   | 0.79   |
| Median Filter  | 23.9   | 0.82   |
| Bilateral      | 25.1   | 0.84   |

*(↑ Higher is better)*

---

## 🧰 Dependencies

- Python 
- OpenCV
- NumPy
- Matplotlib
- scikit-image



