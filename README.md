# Carlitz-Extensiveness

Resolving the remaining cases of Carlitz-extensiveness over finite fields using SageMath.

This repository accompanies the talk *Resolving the Remaining Cases of Carlitz-Extensiveness over Finite Fields using SageMath* (F. Hellwig and M. Schaller), to be presented at **ACA 2026** (Prishtina, 1–5 June 2026).

## Files

- **`Abstract_ACA_2026.pdf`** – Conference abstract submitted to ACA 2026, summarising the background, contribution, and method.
- **`Cases_Solved.ipynb`** – Solution to the remaining cases of Carlitz-extensiveness. Only the deterministic approach is implemented; all additional code has been omitted.
- **`Complete_code_with_benchmarking.ipynb`** – The entire revised code with three methods: deterministic exhaustive search, probabilistic exhaustive search (Las Vegas), and kernel approach. A short benchmark is also included for convenience.
- **`General_Pseudocode_concise.txt`** – Pseudocode covering the most important ideas and steps. Read this if you want to understand the underlying algorithm.
- **`General_Pseudocode_extensive.txt`** – More detailed pseudocode, also explaining additional parameters of the main function. Read this if you want to understand the implemented function.

## Background

The primitive normal basis theorem (Lenstra–Schoof, 1987) asserts the existence of elements in a finite extension of finite fields that simultaneously generate the multiplicative group and a normal basis over the base field. Hsu and Nan (2011) proposed a Carlitz-module analogue, leaving one confirmed exception – $(q, n) = (2, 2)$ – and a finite list of undecided cases. Hachenberger (2016) and subsequent SageMath computations by Gruber reduced the open problem to six remaining pairs. This work resolves those final six cases, confirming the Carlitz-module analogue of the primitive normal basis theorem in all cases except $(q, n) = (2, 2)$.

See `Abstract_ACA_2026.pdf` for full references.
