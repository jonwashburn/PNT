Subject: Contribution to PNT+: Hadamard Factorization & Analytic Bounds (Pre-formalized Bundle)

Dear Professor Tao and PNT+ Contributors,

I am writing to contribute a set of pre-formalized Lean modules to the PrimeNumberTheoremAnd (PNT+) project, specifically targeting the "Hadamard factorization" milestone (Chapter 3 of the blueprint) which currently appears to be a gap in the repository.

These modules were authored by me in October 2025 as part of my independent research on the Riemann Hypothesis. Given the recent activity on the PNT+ repository and the open need for Hadamard factorization infrastructure, I have packaged these files into a clean bundle that aligns with your project's goals.

### What is included in this bundle?

1. **`WeierstrassProduct.lean`**:
   - Bridges between summable series and infinite products (e.g. `tprod_exp_of_summable`, `exp_tsum_eq_tprod`).
   - Rewrites the 2‑modified Euler factor `(1 - z) * exp(z + z^2/2)` as a single exponential of a log remainder.
   - Proves the cubic tail bound `‖log(1 - z) + z + z^2/2‖ ≤ ‖z‖^3 / (1 - ‖z‖)` on `‖z‖ < 1`.

2. **`Determinant.lean`**:
   - Defines `det2_AF(s)` as the Euler product over primes with local factor `(1 - λ) * exp(λ + λ^2 / 2)` for `λ = p^(-s)`.
   - **Crucially:** Proves analyticity and non-vanishing on `Re(s) > 1/2`, including a critical-line specialization.

3. **`GammaBounds.lean`**:
   - Provides `BoundedFGammaPrimeOnStrip`, a Prop-level interface for uniform bounds on the Archimedean factor `Γ(s/2) * π^(-s/2)` on vertical strips, plus an explicit nonnegative constant constructor (Cauchy-route outline).

### How this fits PNT+

- **HadamardFactorization.lean**: This file is currently a placeholder in your repo. My `WeierstrassProduct` and `Determinant` modules provide the necessary infinite product machinery and the specific Euler product analysis to fill this file.
- **Explicit Estimates**: The `GammaBounds` module provides the analytic control needed for explicit $\zeta$ bounds.

### Provenance & Authorship

This code is my work (Jonathan Washburn), completed prior to October 31, 2025, and packaged directly from my existing Lean development. The files contain no `sorry`/`admit`/`axiom` placeholders.

The attached zip file `pnt_submission_bundle.zip` contains the source files and a README with integration instructions.

Best regards,

Jonathan Washburn
washburn.jonathan@gmail.com
