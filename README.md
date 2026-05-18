# 🧬 TopoChip Cell-Material Interaction Analysis


**High-throughput screening of 5,676 micro-topographical surfaces to identify optimal biomaterial designs for cell health and tissue engineering applications.**

This project analyzes TopoChip data to evaluate how different surface topographies affect cell morphology and health. Using morphological feature extraction, composite health scoring, and machine learning classification, we identify the most biocompatible surface designs.

---

## 📌 Table of Contents

- [Key Findings](#-key-findings)
- [Dataset Overview](#-dataset-overview)
- [Cell Health Metrics](#-cell-health-metrics)
- [Surface Ranking Results](#-surface-ranking-results)
- [Machine Learning Model](#-machine-learning-model)
- [Feature Importance](#-feature-importance)
- [Correlation Analysis](#-correlation-analysis)
- [Methodology](#-methodology)
- [Installation](#-installation)
- [Usage](#-usage)
- [Conclusion](#-conclusion)
- [Future Work](#-future-work)
- [Citation](#-citation)

---

## 🏆 Key Findings

| Metric | Value |
|--------|-------|
| **Total Cells Analyzed** | 39,204 |
| **Cells After QC** | 1,012 |
| **Unique Surfaces** | 837 |
| **Best Surface ID** | 1162 |
| **Best Surface Health Score** | **0.854** |
| **Model Accuracy** | **96.6%** |
| **Top Feature** | Cell Area (37.2% importance) |

---

## 📊 Dataset Overview

| Property | Details |
|----------|---------|
| **Source** | Zenodo 15690319 (2025 study) |
| **File** | `imageWithFIdx.csv` (3.56 GB) |
| **Total Cells (raw)** | 39,204 |
| **Total Cells (after QC)** | 1,012 |
| **Total Columns** | 5,570 |
| **Unique Surfaces Tested** | 837 |

---

## 📈 Cell Health Metrics

### Distribution Analysis

| Metric | Mean | Std | Min | Max |
|--------|------|-----|-----|-----|
| **Cell Area** (pixels) | 8,957.6 | 4,677.4 | 592 | 19,951 |
| **Cell Perimeter** (pixels) | 812.4 | 320.9 | 91 | 1,577 |
| **Circularity** (1 = perfect circle) | **0.197** | 0.11 | 0.10 | 0.90 |
| **Nucleus Area** (pixels) | 1,998.9 | 858.4 | 185 | 6,201 |
| **Nucleus-to-Cell Ratio** | **0.264** | 0.13 | 0.10 | 0.79 |
| **Health Score** | **0.524** | 0.114 | 0.141 | 0.878 |

### Distribution Visualizations

#### Cell Area Distribution
<img width="617" height="420" alt="image" src="https://github.com/user-attachments/assets/c3d83052-fc21-4111-bfec-6bb4a752e254" />


*Right-skewed distribution with mean of 8,958 pixels*

#### Cell Circularity Distribution
<img width="607" height="437" alt="image" src="https://github.com/user-attachments/assets/528a93a7-f4a2-443d-ad23-904cc4331df6" />


*Peaks at low values (0.1-0.3), indicating elongated cells*

#### Nucleus-to-Cell Ratio Distribution
<img width="593" height="431" alt="image" src="https://github.com/user-attachments/assets/748b858e-871f-4791-9de0-aa638e3a3a77" />


*Normal-like distribution centered at 0.264*

### Key Insights

- **Low mean circularity (0.197)** indicates cells are predominantly elongated on tested surfaces
- **Nucleus-to-cell ratio (0.264)** suggests healthy cell spreading
- **Health score distribution** shows a wide range, enabling clear surface differentiation

---

## 🏆 Surface Ranking Results

### Top 10 Surfaces (Best for Cell Health)

| Rank | Surface ID | Health Score |
|------|------------|--------------|
| 1 | **1162** | **0.854** |
| 2 | 1437 | 0.830 |
| 3 | 561 | 0.807 |
| 4 | 1173 | 0.772 |
| 5 | 98 | 0.768 |
| 6 | 951 | 0.763 |
| 7 | 336 | 0.744 |
| 8 | 2073 | 0.739 |
| 9 | 1405 | 0.734 |
| 10 | 306 | 0.733 |

### Bottom 10 Surfaces (Worst for Cell Health)

| Rank | Surface ID | Health Score |
|------|------------|--------------|
| 828 | 1523 | 0.263 |
| 829 | 1966 | 0.262 |
| 830 | 622 | 0.255 |
| 831 | 1919 | 0.231 |
| 832 | 237 | 0.229 |
| 833 | 487 | 0.224 |
| 834 | 1140 | 0.221 |
| 835 | 1563 | 0.220 |
| 836 | 265 | 0.190 |
| 837 | 2017 | **0.174** |

### Top 30 Surfaces Ranked by Cell Health

<img width="1230" height="497" alt="image" src="https://github.com/user-attachments/assets/6290c6c8-9acf-40cf-bf4c-0a800128e779" />


*Bar chart showing average cell health scores for the top 30 performing surfaces*

---

## 🤖 Machine Learning Model

### Model Configuration

| Parameter | Value |
|-----------|-------|
| **Algorithm** | Random Forest Classifier |
| **Training Samples** | 1,012 |
| **Test Split** | 80/20 |
| **Number of Trees** | 100 |
| **Features** | 5 morphological metrics |

### Performance Metrics

| Metric | Value |
|--------|-------|
| **Accuracy** | **96.6%** |
| **Precision (Class 0)** | 0.95 |
| **Recall (Class 0)** | 0.98 |
| **Precision (Class 1)** | 0.98 |
| **Recall (Class 1)** | 0.95 |
| **F1-Score (Macro Avg)** | 0.97 |


