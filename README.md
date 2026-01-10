---

# DWT_hologram

This repository contains the implementation associated with the paper:

**“[Title of the paper]”**
arXiv:2211.09938
*(Optica FIO implementation)*

The code demonstrates **pixel-based hologram generation using dictionary learning and discrete wavelet transform (DWT)** with optional **GPU acceleration (CuPy)**. The main implementation is provided as a Jupyter notebook for reproducibility and experimentation.

---

## 📌 Overview

The notebook implements a **dictionary-based hologram generation framework** for grayscale images, including:

* Pixel-wise hologram synthesis
* Multi-resolution dictionary construction (1×1, 2×2, 4×4, 8×8 blocks)
* Saliency-guided processing
* Physics-based spherical wave propagation
* GPU acceleration support using **CuPy**
* MATLAB-compatible `.mat` file export

This code is primarily intended for **research and experimental use**.

---

## 📂 Repository Structure

```
DWT_hologram/
│
├── pixel_iccasp_gpu_cupy.ipynb   # Main notebook (core implementation)
├── pairs_of_saliency/            # Input images and saliency maps (user-provided)
├── matfile/                      # Output MATLAB files
└── README.md
```

---

## ⚙️ Requirements

### Python Dependencies

* Python ≥ 3.7
* NumPy
* SciPy
* OpenCV (`cv2`)
* Matplotlib
* scikit-image
* Jupyter Notebook

Optional (for GPU acceleration):

* CuPy (CUDA-enabled GPU required)

```bash
pip install numpy scipy matplotlib opencv-python scikit-image jupyter
```

For GPU support:

```bash
pip install cupy-cuda11x
```

> ⚠️ Make sure your CUDA version matches your CuPy installation.

---

## 🚀 How to Run

1. Clone the repository:

```bash
git clone https://github.com/ShimaRafiei-IUT/DWT_hologram.git
cd DWT_hologram
```

2. Launch Jupyter Notebook:

```bash
jupyter notebook
```

3. Open:

```
pixel_iccasp_gpu_cupy.ipynb
```

4. Prepare input data:

   * Place grayscale images in `pairs_of_saliency/`
   * Provide corresponding saliency maps with `_sal_fuse` suffix

Example:

```
0945.jpg
0945_sal_fuse.png
```

5. Run cells sequentially.

---

## 🧠 Method Summary

### Hologram Generation

The function `digitalHologramGeneration_gray()` computes a **complex hologram field** by superposition of spherical waves emitted from object points:

* Physically accurate wave propagation
* Distance-dependent amplitude decay
* Aperture-limited contribution (Rmax constraint)

### Dictionary Construction

The function `Complete_dictionary_gray()` constructs hologram dictionaries at multiple spatial resolutions:

* 1×1 (single pixel)
* 2×2
* 4×4
* 8×8

Each dictionary atom corresponds to a point source at a given depth.

---

## 🖥️ GPU Acceleration

The notebook is written to be **CuPy-compatible**.
By switching NumPy to CuPy (`import cupy as cp`), large hologram computations can be accelerated on GPU.

---

## 📊 Output

* Complex holograms
* Visualizations of amplitude/intensity
* `.mat` files for MATLAB-based reconstruction or analysis

---

## 📄 Citation

If you use this code in your research, please cite:

```bibtex
@article{rafiei2022dwt,
  title={Title of the Paper},
  author={Rafiei, Shima and others},
  journal={arXiv preprint arXiv:2211.09938},
  year={2022}
}
```

---

