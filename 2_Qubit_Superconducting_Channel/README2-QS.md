# Reference-Free Noise Calibration for Two-Qubit Superconducting Channels

**Crosstalk Detection via Self-Consistent 16×16 Pauli Transfer Matrix Reconstruction**

Extension of the single-qubit reference-free calibration framework to realistic superconducting hardware, with a built-in locality diagnostic for detecting ZZ crosstalk.

---

## 📌 Overview

This project extends the single-qubit noise calibration method to **two coupled qubits**, directly addressing one of the biggest challenges in superconducting quantum hardware: **crosstalk**.

It demonstrates how to:
- Reconstruct the full **16×16 Pauli Transfer Matrix (PTM)** self-consistently from 36 calibration states (no assumed noise model).
- Use realistic superconducting parameters (T₁, T₂, gate times, readout errors).
- Detect **static ZZ crosstalk** using a **locality residual** (D-criterion gap) that compares the full reconstruction against the best local (tensor-product) model.

Inspired by the same thesis philosophy (*Balanced Homodyne Detection without a Coherent State Local Oscillator*), this work shows how self-consistent reconstruction and consistency diagnostics scale to multi-qubit systems.

---

## 🎯 Key Features

- **16×16 Self-Consistent PTM Reconstruction** — Linear inversion over 36 product states (over-determined for robust D-criterion).
- **Superconducting-Realistic Noise Model** — T₁ = 80 µs, T₂ = 50 µs, 300 ns gate time, 2% readout error.
- **Crosstalk Sensor** — Static ZZ coupling (0–400 kHz) injected; locality gap (`D_local - D_full`) reliably detects non-local dynamics.
- **Locality Diagnostic** — Quantifies how much of the observed noise cannot be explained by independent single-qubit channels.
- **Scaling & Visualization** — PTM heatmaps, crosstalk residual maps, and ZZ-coupling scans.

---

## 🚀 Real-World Advantages

- **Crosstalk Detection Without Dedicated Experiments**: The same calibration data used for PTM reconstruction also reveals ZZ crosstalk via the locality gap.
- **Improved Error Mitigation**: Reconstructed PTMs (full + local decomposition) can feed directly into Zero-Noise Extrapolation (ZNE), Probabilistic Error Cancellation, or noise-aware compilation.
- **Hardware Relevance**: Mirrors challenges in fixed-frequency transmon architectures (IBM, Google, Rigetti, etc.).
- **Scalability Foundation**: Natural stepping stone toward larger qubit arrays and crosstalk mapping.

---

## 📊 Results Highlights

- The full 16×16 model remains consistent (low `D_full`) even with crosstalk.
- The **locality gap** grows monotonically with ZZ coupling strength — an effective, model-free crosstalk sensor.
- Reconstruction accurately captures both local relaxation/dephasing and coherent ZZ-induced correlations.

**Figures**:
- **Fig 5**: 16×16 PTM comparison (Ground Truth vs Reconstructed vs Best Local)
- **Fig 6**: Crosstalk fingerprint (PTM residual = Full - Local)
- **Fig 7**: Locality gap vs ZZ coupling strength

---

## 🛠️ Installation & Usage

### Requirements
```bash
pip install qutip numpy matplotlib
