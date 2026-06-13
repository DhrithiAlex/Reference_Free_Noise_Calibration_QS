# Project Figures Documentation

This file provides clear descriptions of all generated figures from both the single-qubit and two-qubit noise calibration projects.

---

## Single-Qubit Reference-Free Noise Calibration

### Figure 1: Pauli Transfer Matrix (PTM) Comparison
**Description:**  
Comparison of the Pauli Transfer Matrix (PTM) for the noisy qubit channel. The **left panel** shows the ground-truth PTM (noise-free simulation), the **center panel** displays the self-consistently reconstructed PTM using only measured data, and the **right panel** shows the naive "ideal instrument" assumption (identity matrix). The self-consistent reconstruction accurately captures the effects of amplitude damping and dephasing, achieving significantly lower error than the naive approach.

### Figure 2: Calibration States on the Bloch Sphere
**Description:**  
Visualization of the six calibration states (±X, ±Y, ±Z) on the Bloch sphere. **Blue points** represent the ideal input states, while **red points** show the measured noisy output states after the channel is applied. The inward contraction of the red points toward the center illustrates the decoherence induced by the noisy channel. Dashed lines connect corresponding input-output pairs, highlighting the geometric effect of the quantum noise.

### Figure 3: Reconstruction Accuracy vs. Measurement Budget
**Description:**  
Scaling of reconstruction performance with the number of measurement shots. The **left plot** shows the Frobenius-norm error of the reconstructed PTM versus the ground truth (blue) compared to the naive assumption (gray dashed line). The **right plot** displays the D-criterion residual as a function of shots. Both metrics improve steadily with increased measurement budget, demonstrating that useful calibration can be achieved with modest resources.

### Figure 4: D-Criterion as a Non-Markovianity Diagnostic
**Description:**  
Bar plot comparing the D-criterion residual in the standard Markovian case (Lindblad noise only) versus the non-Markovian case (with injected state-dependent error). The D-criterion increases by approximately **two orders of magnitude** (~200×) when the noise cannot be described by a single linear map. This highlights its effectiveness as a diagnostic tool for detecting complex noise sources such as crosstalk or calibration drift.

---

## Two-Qubit Superconducting Noise Calibration

### Figure 5: Two-Qubit Pauli Transfer Matrix Comparison
**Description:**  
Comparison of the 16×16 Pauli Transfer Matrix (PTM) for a two-qubit channel with static ZZ crosstalk. The **left panel** shows the ground-truth PTM, the **center panel** displays the self-consistently reconstructed PTM from calibration data, and the **right panel** shows the best local (tensor-product) approximation. All matrices are diagonally dominant, but subtle differences in the full vs. local versions reveal the presence of two-qubit correlations.

### Figure 6: Crosstalk Fingerprint (PTM Residual)
**Description:**  
PTM residual obtained by subtracting the best local (tensor-product) approximation from the ground-truth PTM. Non-zero entries highlight the genuinely two-qubit (non-local) components induced by the static ZZ coupling. The pattern — particularly in blocks involving X/Y ↔ Z correlations — serves as a clear "fingerprint" of coherent crosstalk that cannot be captured by independent single-qubit noise models.

### Figure 7: Locality Gap vs. ZZ Coupling Strength
**Description:**  
Scaling study showing how the D-criterion residuals respond to increasing static ZZ coupling (0–400 kHz). The **left plot** compares the full 16×16 self-consistency residual (D_full, remains flat at shot-noise level) versus the local model residual (D_local, grows with crosstalk). The **right plot** isolates the **locality gap** (D_local − D_full), demonstrating its effectiveness as a sensitive, model-free sensor for detecting two-qubit crosstalk.

---

**Notes:**
- All figures were generated automatically by running `qubit_noise_calibration.py` and `qubit_noise_calibration_2q.py`.
- These visualizations support the core claims of the project: self-consistent reconstruction without trusted references and powerful diagnostic residuals (D-criterion and locality gap).

For more context, refer to the main `README.md` and the project PDFs.
