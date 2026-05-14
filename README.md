# Carlitz-Extensiveness

Resolving the remaining cases of Carlitz-extensiveness over finite fields using SageMath.

This repository accompanies the talk *Resolving the Remaining Cases of Carlitz-Extensiveness over Finite Fields using SageMath* (F. Hellwig and M. Schaller), presented at **ACA 2026** (Prishtina, 1–5 June 2026).

## Files and structure

- **`Abstract_ACA_2026.pdf`** – Conference abstract submitted to ACA 2026, summarising the background, contribution, and method.

- **`ACA_Presentation.pdf`** – Slides of the ACA 2026 presentation. These slides give a detailed and accessible overview of the historical context, the mathematical background and the computational strategy to solve the remaining cases of Carlitz-extensiveness. Readers looking for a guided explanation of the algorithms and the underlying ideas are encouraged to start here.

- **`Remaining_cases_solved_original_code.ipynb`** – Minimal notebook resolving the remaining cases of Carlitz-extensiveness. It contains only the deterministic approach needed for the final verification; additional benchmarking and auxiliary code have been omitted.

- **`Original_complete_code_with_benchmarking.ipynb`** – Full implementation of the main algorithm, including the deterministic exhaustive search, the randomized Las Vegas variant, and the kernel-based approach. A short benchmark suite is included for convenience.

- **`Alternative_Code_with_Benchmarking_and_Results.ipynb`** – Alternative implementation for the same decision problem. This version first finds one tau-generator for each operator \(\gamma_z\), then searches for primitive tau-generators via cyclic module coordinates. It also contains benchmark utilities and precomputed benchmark results. The benchmark runs are disabled by default.

### Original implementation files

The folder **`Original_code_results_and_pseudocode/`** contains supplementary files for the original implementation:

- concise and extensive pseudocodes for the main algorithm,
- benchmarking CSV file,
- benchmarking plot,
- CSV file documenting the computations for the remaining cases.

In particular:

- **`Original_Pseudocode_concise.txt`** – Concise pseudocode for the main algorithm. Read this first for a compact overview of the key ideas and steps.

- **`Original_Pseudocode_extensive.txt`** – More detailed pseudocode for the main algorithm, including additional parameters and implementation details.

### Alternative implementation files

The folder **`Alternative_code_results_and_pseudocode/`** contains supplementary files for the alternative implementation:

- pseudocode for the alternative algorithm,
- benchmarking CSV file,
- benchmarking plot,
- CSV file documenting the computations for the remaining cases.

In particular:

- **`Alternative_Pseudocode.txt`** – Pseudocode for the alternative implementation. It explains the second strategy: after finding one tau-generator \(u\), the algorithm generates candidates of the form \(a(\gamma_z)u\), where \(a\) ranges over suitable monic polynomials, and then tests these candidates and their nonzero \(F_q\)-scalar multiples for multiplicative primitivity.

## Background

The primitive normal basis theorem (Lenstra–Schoof, 1987) asserts the existence of elements in a finite extension of finite fields that simultaneously generate the multiplicative group and a normal basis over the base field.

Hsu and Nan (2011) proposed a Carlitz-module analogue, leaving one confirmed exception, \((q, n) = (2, 2)\), and a finite list of undecided cases. Hachenberger (2016) and subsequent SageMath computations by Gruber reduced the open problem to six remaining pairs.

This work resolves those final six cases, confirming the Carlitz-module analogue of the primitive normal basis theorem in all cases except \((q, n) = (2, 2)\).

See `Abstract_ACA_2026.pdf` for full references. For a more explanatory overview of the ideas and computations, see `ACA_Presentation.pdf`.

## Implementation notes

All notebooks are written for SageMath. They should be run with a SageMath/Python kernel.

The repository contains two algorithmic implementations for the same decision problem:

1. The main implementation, described in `Original_code_results_and_pseudocode/General_Pseudocode_concise.txt` and `Original_code_results_and_pseudocode/General_Pseudocode_extensive.txt`, searches over primitive projective representatives and tests tau-generatorhood.

2. The alternative implementation, described in `Alternative_code_results_and_pseudocode/Alternative_Pseudocode.txt`, first finds one tau-generator and then searches within the corresponding cyclic \(F_q[t]\)-module for a primitive tau-generator.

The benchmark notebooks contain precomputed outputs. Long benchmark runs are disabled by default and should only be enabled deliberately.

The supplementary folders also contain benchmarking plots, benchmarking CSV files, and CSV files recording the computations for the remaining cases. These files are included to make the computational evidence and performance comparisons transparent and reproducible.
