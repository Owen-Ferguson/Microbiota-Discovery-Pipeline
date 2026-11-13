# Analysis inputs


| Input path | Expected structure |
| --- | --- |
| `data/Mouse_Data_For_PCA.xlsx` | First worksheet with one row per sample. Metadata columns are `Full ID`, `Group`, `Timepoint`, and `Sex`. The remaining columns are bacterial family abundances. The original group labels are `B6` and `M83(ho)`, and timepoint labels are `2 Months` and `4 Months`. |
| `data/Human_RawData_for_PCA_SALIVA.xlsx` | First worksheet with one row per saliva sample. Metadata columns are `SampleID`, `Age`, `Gender`, `Treatment`, `Disease_Duration`, `Symptom_Duration`, `H_Y_Score`, and `Collection`. The remaining columns are bacterial family abundances. Preserve the original `Control` and `Parkinson` treatment labels. |
| `data/Human_RawData_for_PCA_SWAB.xlsx` | Human oral swab workbook with the same column structure as saliva. |
| `data/Human_RawData_for_PCA_ERG.xlsx` | First worksheet with `SampleID` and ERG measures. The classifier notebook uses this file to reconstruct the original cohort and complete-case exclusions. The join uses the first six characters of the saliva IDs and the ERG workbook IDs as supplied. Keep the original row order and missing values. |
| `data/sequencing/LEVM009/*.fastq.gz` | Original saliva FASTQ set. The sequencing-depth notebook counts records in files whose paths contain `OM-501`, then calculates the mean and sample SD across files. |

The notebooks work from the prepared family-level abundance workbooks. Upstream sequence processing is described in the manuscript. The `outputs/` directory is generated locally and can contain participant- or animal-level results.
