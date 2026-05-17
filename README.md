# A Machine Learning Framework for Early Detection of Food Insecurity Using Administrative Microdata

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

---

**Autores:**  
Keila Barbosa¹˒³, André L. Aquino¹

¹ Orion Lab., Instituto de Computação  
Universidade Federal de Alagoas (UFAL), Maceió – AL – Brasil

² Centro de Informática  
Universidade Federal de Pernambuco (UFPE), Recife – PE – Brasil

**Evento:**  
CSBC 2026 – LASDigiGov

---

Food insecurity is a multidimensional phenomenon strongly associated with socioeconomic, household, and territorial factors.

This repository presents a complete machine learning pipeline designed to predict food insecurity risk using administrative microdata from Brazil’s Cadastro Único (CadÚnico), focusing on the state of Alagoas.

The proposed framework integrates:

- Data preprocessing
- Feature engineering
- Predictive modeling
- Temporal evaluation
- Explainability using SHAP
- Spatial aggregation and analysis

The experiments evaluate both linear and tree-based machine learning models, including:

- Logistic Regression
- Random Forest
- LightGBM
- CatBoost

A temporal evaluation protocol is adopted using:

- **2024** data for training/validation
- **2025** data for testing

This strategy improves temporal realism and generalization.

The final **LightGBM** model achieved:

| Metric | Value |
|---|---|
| ROC-AUC | 0.91 |
| PR-AUC | 0.72 |
| Recall | 0.78 |

Results demonstrate strong capability in identifying households at risk of food insecurity.

Interpretability analyses reveal the importance of territorial and socioeconomic variables, while spatial aggregation highlights geographic patterns of vulnerability.

The proposed framework supports:

- Early warning systems
- Public policy planning
- Data-driven social assistance strategies

---

# Repository Structure

```text
CADUNICOIA
│
├── anon_outputs
│   Aggregated and anonymized outputs generated during analyses
│
├── BR_Municipios_2024
│   Brazilian municipalities shapefiles (IBGE)
│
├── catboost_info
│   CatBoost training logs and metadata
│
├── outputs
│   Final outputs, predictions, figures, and exported results
│
├── notebook1
│   Intermediate experimental notebooks and auxiliary analyses
│
├── notebook2
│   Additional experiments and exploratory analyses
│
├── notebook3
│   Explainability and complementary analyses
│
├── .gitignore
│
├── 01_preprocess_and_baselines.ipynb
│   Data preprocessing and baseline models
│
├── 02_model_comparison_and_final.ipynb
│   Model comparison and final evaluation experiments
│
├── 03_explainability_and_ablation.ipynb
│   SHAP explainability and ablation studies
│
├── limpezaDados.ipynb
│   Data cleaning and preparation notebook
│
├── maceio_ACC_250km_01h_20260225202002.tif
│   Geospatial raster data used in spatial analyses
│
├── requirements.txt
│   Project dependencies
│
└── README.md
```

---

# Data Availability

Due to privacy restrictions and the sensitive nature of administrative microdata, the complete datasets are not publicly distributed in this repository.

The processed and auxiliary files can be accessed at:

```text
https://drive.google.com/drive/folders/1sQwPOXon2Nz4FvgBTbP_4aMwpdO9JPZj?usp=sharing
```

Expected directory structure:

```text
data/
    data_original/
    anon_outputs/
    BR_Municipios_2024/
```

---

# Methodology

The proposed pipeline follows the steps below:

## 1. Data Ingestion

- Importation of CadÚnico administrative microdata
- Integration of territorial and household information

## 2. Data Cleaning and Preparation

- Missing value treatment
- Variable standardization
- Feature transformation
- Encoding categorical variables

## 3. Feature Engineering

- Socioeconomic indicators
- Household composition variables
- Territorial vulnerability indicators
- Temporal features

## 4. Predictive Modeling

The following models were evaluated:

- Logistic Regression
- Random Forest
- LightGBM
- CatBoost

## 5. Temporal Evaluation

- Training and validation using 2024 data
- Temporal testing using 2025 data

## 6. Explainability

- SHAP value analysis
- Feature importance interpretation
- Global and local explainability

## 7. Spatial Analysis

- Municipal aggregation
- Spatial visualization
- Geographic vulnerability mapping

## 8. Visualization

- Statistical plots
- SHAP plots
- Spatial maps
- Performance comparison figures

---

# Requirements

Recommended Python version:

```text
Python >= 3.10
```

Main libraries used:

```text
pandas
numpy
scikit-learn
lightgbm
catboost
matplotlib
seaborn
geopandas
shap
scipy
jupyter
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install pandas numpy scikit-learn lightgbm catboost matplotlib seaborn geopandas shap scipy jupyter
```

---

# Running the Project

Clone the repository:

```bash
git clone https://github.com/your-repository/CADUNICOIA.git
cd CADUNICOIA
```

Recommended notebook execution order:

```text
1. limpezaDados.ipynb
2. 01_preprocess_and_baselines.ipynb
3. 02_model_comparison_and_final.ipynb
4. 03_explainability_and_ablation.ipynb
```

---

# Main Results

The repository reproduces:

- Temporal machine learning experiments
- Baseline comparisons
- Explainability analyses
- Spatial aggregation analyses
- Geographic visualization of food insecurity risk

Generated outputs include:

- ROC curves
- Precision-Recall curves
- SHAP plots
- Municipality-level risk maps
- Aggregated prediction tables

Outputs are stored in:

```text
outputs/
anon_outputs/
```

---

# Acknowledgements

This study was funded in part by the Fundação de Amparo à Pesquisa do Estado de Alagoas (FAPEAL), under grant E:60030.0000000352/2021, and by the Conselho Nacional de Desenvolvimento Científico e Tecnológico (CNPq), under grant 407515/2022-4.

The authors also thank Orion Lab., the Federal University of Alagoas (UFAL), and the Federal University of Pernambuco (UFPE) for institutional and scientific support.

---

# License

This project is licensed under:

**Creative Commons Attribution 4.0 International Public License (CC BY 4.0)**

You are free to:

- Share
- Adapt
- Redistribute
- Reuse the content

Provided proper attribution is given to the authors.

More information:

```text
https://creativecommons.org/licenses/by/4.0/
```

---

# Citation

If you use this repository, code, or results in academic work, please cite:

```bibtex
@inproceedings{barbosa2026foodinsecurity,
  title={A Machine Learning Framework for Early Detection of Food Insecurity Using Administrative Microdata},
  author={Barbosa, Keila and Aquino, Andre L.},
  booktitle={Anais do CSBC 2026 -- LASDigiGov},
  year={2026},
  organization={Sociedade Brasileira de Computação},
  license={CC BY 4.0}
}
```