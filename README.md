# SPHERE staged biomarker testing

Completed exploratory research package — November 9, 2026.

Open **outputs/FINAL_REPORT.html** for the self-contained final report, tables, figures, interpretation and limitations. All figures are also in outputs/figures. The verified results are internal synthetic-data benchmarks, not a clinically validated tool.

## Main finding

On 348 synthetic records, p-tau217-only logistic regression had mean AUROC 0.772. Staged addition of GFAP and NfL did not improve the observed error–measurement tradeoff. Extra biomarkers improved the nonlinear comparator relative to its one-feature version, but did not beat the logistic reference. This is an exploratory negative result, not proof that those biomarkers lack clinical value.

## Reproduce locally

Use Python 3.13 (the development environment was Python 3.13 on macOS). Other platforms have not been tested.

```sh
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements.txt
.venv/bin/python scripts/prepare_data.py /path/to/ADRC_SPHERE_all_data.zip
.venv/bin/python scripts/run_all.py
```

Obtain the official archive through your own authorized Stanford access. No raw data or API keys are included in the deliverable. The runner uses local files only and stops on failures. Source hashes, pinned package versions and evaluation seeds are recorded. Bootstrap installation needs network access; analysis does not.

## Contents

- `scripts/`: data preparation, seven analysis stages, verification and report generation.
- `docs/`: methods, assumptions, model card and external-validation plan.
- `outputs/`: aggregate metrics, reports and figures. Local record-level predictions are generated for checking but excluded from the packaged deliverable.
- `requirements.txt`: exact installed dependency versions.

## Scope and limitations

Completed: structural data audit, baseline, split/threshold checks, staged testing, error analysis, feature ablations, nonlinear comparison, calibration, descriptive age/sex summaries, label-shuffle sanity controls, reconciliation and final report.

Not completed or claimed: confirmed assay units/missing codes, independent real-data validation, clinical or economic validation, fairness certification, proof of research novelty or publication. The user authorized continued exploratory work under explicit data assumptions. No new agreement or contact is required for the completed local study. ADNI is a documented future validation option requiring separate authorized access.

Signed exported values are retained. Outcome is probable-AD-versus-control classification, not prediction of future disease. Repeated exploration of the same release makes all comparisons discovery findings.

## Governance

This package and its private GitHub repository are for internal review. Aggregate reports and figures are versioned; raw tables, record-level predictions, logs, and local environments remain excluded. Stanford’s accepted agreement includes restrictions on data redistribution and review requirements before public disclosure of results. Do not publish the archive or reports automatically. The package excludes raw tables, credentials, local predictions, environment binaries and caches.

Acknowledgment: Stanford Alzheimer’s Disease Research Center, NIH/NIA grant P30 AG066515. Source: https://adrc-sphere.stanford.edu/ . Methods: https://pmc.ncbi.nlm.nih.gov/articles/PMC13596149/ .
