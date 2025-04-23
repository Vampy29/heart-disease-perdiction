# 🗂️ Healthcare Analysis

This project utilizes multiple datasets related to clinical diagnoses, procedures, and healthcare billing codes. Below is a description of each dataset used.

---

## 📁 Data Files

### 1. final_data1.csv
- A merged or processed dataset likely containing patient-level data used for final modeling or analysis.
- Expected to include identifiers, diagnosis/procedure codes, and possibly outcomes or cost variables.

### 2. d_icd_diagnoses.csv
- Contains metadata or descriptions for ICD diagnosis codes.
- Columns may include:
  - icd_code
  - long_title
  - short_title

### 3. d_icd_procedures.csv
- Contains metadata for ICD procedure codes.
- Columns may include:
  - icd_code
  - category
  - description

### 4. diagnoses_icd.csv
- Likely a mapping of patient encounters to ICD diagnosis codes.
- May include:
  - subject_id
  - hadm_id
  - seq_num (diagnosis order)
  - icd_code

### 5. procedures_icd.csv
- Similar to `diagnoses_icd.csv`, but for medical procedures.
- May include:
  - subject_id
  - hadm_id
  - seq_num
  - icd_code

### 6. drgcodes.xlsx
- Likely contains DRG (Diagnosis Related Groups) billing codes.
- May include:
  - drg_code
  - description
  - version
  - hadm_id

---

## 📚 Data Reference

The structure and inspiration for the datasets can be referenced from:

**[PubMed Central - PMC11979112](https://pmc.ncbi.nlm.nih.gov/articles/PMC11979112/)**  
"Data, Data Everywhere, but Access Remains a Big Issue for Researchers" – a study discussing the landscape of clinical datasets and accessibility for research.

---

## 🧠 Use Cases

- Join raw ICD codes with `d_icd_diagnoses` or `d_icd_procedures` for human-readable descriptions.
- Analyze comorbidity patterns or treatment plans from `diagnoses_icd` and `procedures_icd`.
- Use `final_data1.csv` as the cleaned, analysis-ready dataset.
- Use `drgcodes.xlsx` to explore billing or grouping trends by diagnosis-related groups.

---

## 🔧 Suggested Tools & Libraries

- pandas
- openpyxl (for reading Excel files)
- matplotlib / seaborn (for visualizations)

---

## 🚀 Getting Started

1. Place all datasets in a `data/` folder.
2. Load them using pandas:

```python
import pandas as pd

diagnoses = pd.read_csv("data/diagnoses_icd.csv")
procedures = pd.read_csv("data/procedures_icd.csv")
diag_desc = pd.read_csv("data/d_icd_diagnoses.csv")
proc_desc = pd.read_csv("data/d_icd_procedures.csv")
drg = pd.read_excel("data/drgcodes.xlsx")
final_df = pd.read_csv("data/final_data1.csv")
