# Oral microbiota alterations in early-stage Parkinson’s disease

Analysis notebooks accompanying **Oral microbiota alterations precede neuropathological changes in an alpha-synuclein model and identify candidate biomarkers of early-stage Parkinson’s disease**.

## Run the notebooks

1. From the repository root, create a Python 3.10 virtual environment and install the dependencies.

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   python -m pip install -r requirements.txt
   jupyter lab
   ```

   In Windows PowerShell, activate with `.\.venv\Scripts\Activate.ps1`.
2. Place the original analysis inputs in [`data/`](data/README.md) using the specified filenames. Data access follows the manuscript’s Data availability statement.
3. Open the relevant notebook, restart its kernel and run all cells from top to bottom. Each notebook is self-contained given its inputs. Files are written under `outputs/`. The original plots use Arial and may render with a substitute font when it is unavailable.

## Figure and methods index

| Manuscript item | Notebook | Outputs or scope |
| --- | --- | --- |
| Figure 1a | [Mouse clustering](mouse/01_dendrogram.ipynb) | Ward dendrogram and stacked abundance bars |
| Figure 1b and Supplementary Figure 2a | [Mouse PCA and Z-scores](mouse/02_pca_and_z_scores.ipynb) | PCA with a descriptive decision boundary and a ranked mean Z-score heatmap |
| Figure 2 | [Mouse family abundance](mouse/03_family_abundance.ipynb) | Group and timepoint comparisons, GraphPad-ready CSVs and a Python summary plot |
| Figure 3a | [Saliva clustering](human/01_saliva_dendrogram.ipynb) | Ward dendrogram and stacked abundance bars |
| Figure 3b and Supplementary Figure 2c | [Saliva PCA and Z-scores](human/02_saliva_pca_and_z_scores.ipynb) | PCA and ranked mean Z-score heatmap |
| Supplementary Figures 1a, 1b and 2b | [Swab clustering](human/03_swab_dendrogram.ipynb) and [swab PCA and Z-scores](human/04_swab_pca_and_z_scores.ipynb) | Dendrogram, stacked abundance bars, PCA and ranked mean Z-score heatmap |
| Figure 4 and Supplementary Figure 3 | [Saliva family abundance and correlations](human/05_saliva_family_abundance_and_correlations.ipynb) | Abundance panels, Pearson correlations and a separate Benjamini–Hochberg table |
| Figure 5b–d and Supplementary Figure 4 | [Saliva logistic regression](human/06_saliva_logistic_regression.ipynb) | AUROC, balanced accuracy, bootstrap intervals, ROC, confusion matrix and the feature-count/sex comparison |
| Sequencing methods | [Saliva sequencing depth](human/07_saliva_sequencing_depth.ipynb) | Original FASTQ record counts, mean and sample SD for saliva |

The classifier uses the source notebook’s ERG–saliva join and complete-case cohort. ERG measures affect eligibility and are excluded as model predictors. Feature ranking precedes cross-validation, so performance estimates are exploratory. The source calculates **balanced accuracy** using a Youden threshold selected from the pooled out-of-fold predictions.

The Figure 2 and Figure 4 notebooks generate source tables and panels. The manuscript composites were assembled separately. Clinical scatter plots retain the source notebook’s raw Pearson p-values, while the FDR table reports adjusted values.



