# Hadamard Factorization & Analytic Bounds Bundle for PNT+

This bundle provides a set of pre-formalized Lean modules to fill the "Hadamard factorization" gap in the PrimeNumberTheoremAnd repository.

## Contents

1. **WeierstrassProduct.lean**: 
   - Provides modern bridges between summable series and infinite products (e.g. `tprod_exp_of_summable`, `exp_tsum_eq_tprod`).
   - Rewrites the 2‑modified Euler factor `(1 - z) * exp(z + z^2/2)` as a single exponential of a log remainder.
   - Proves the key cubic tail bound `‖log(1 - z) + z + z^2/2‖ ≤ ‖z‖^3 / (1 - ‖z‖)` on `‖z‖ < 1`.

2. **Determinant.lean**:
   - Defines `det2_AF(s)` as an Euler product over primes with local factor `(1 - λ) * exp(λ + λ^2 / 2)` for `λ = p^(-s)`.
   - Proves analyticity on `Re(s) > 1/2` and non-vanishing on `Re(s) > 1/2`, including the critical line specialization.

3. **ProductLemmas.lean**:
   - Infrastructure for handling infinite products in a group-with-zero setting.

4. **GammaBounds.lean**:
   - Provides `BoundedFGammaPrimeOnStrip`, a Prop-level interface for uniform bounds on the Archimedean factor `Γ(s/2) * π^(-s/2)`, plus an explicit nonnegative constant constructor.

## Integration Plan

- **Self-contained**: This bundle includes a `Common.lean` file with necessary helpers, making the modules self-contained within the `PrimeNumberTheoremAnd` namespace.
- **HadamardFactorization.lean**: Can import `WeierstrassProduct` and `Determinant` directly.
- **ZetaBounds.lean**: Can use `GammaBounds` for explicit estimates.

## Provenance
This code was authored by Jonathan Washburn (pre-October 2025) and is provided to the PNT+ project to accelerate the "Third Approach" (Hadamard factorization) milestone.
