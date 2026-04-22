# Automated Multi-Label ICD Coding from Clinical Notes

**BHI 506 — Machine Learning and AI | Spring 2026**  
Aaradhya Acharya | M.S. Biomedical and Health Informatics, SUNY Oswego

## Overview

Multi-label text classification system for predicting the top 50 most frequent 
ICD-10 diagnosis codes from clinical discharge summaries, using the MIMIC-IV 
dataset. Compares a TF-IDF + Logistic Regression baseline against a fine-tuned 
BioClinicalBERT transformer.

**Key finding:** The TF-IDF baseline outperforms the transformer on all metrics,
primarily because 512-token truncation discards the diagnostically critical 
latter sections of long discharge summaries — consistent with Edin et al. (2023).

## Results

| Metric | TF-IDF + LR (Baseline) | BioClinicalBERT (threshold=0.65) |
|---|---|---|
| Micro-F1 | **0.5303** | 0.4327 |
| Macro-F1 | **0.4179** | 0.4081 |
| Precision@5 | **0.5695** | 0.3998 |
| Recall@5 | **0.6123** | 0.4275 |

## Data Access

Datasets:

https://physionet.org/content/mimiciv/3.1/

https://physionet.org/content/mimic-iv-note/2.2/


This project uses **MIMIC-IV v2.2** and **MIMIC-IV-Note v2.2**, which require:
1. A credentialed PhysioNet account: https://physionet.org
2. Completion of the CITI "Data or Specimens Only Research" training
3. Signing the data use agreement for each dataset

Data files are **not included** in this repository. After access is granted,
place files as follows:
