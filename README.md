# Anomaly Detection in Database Access Logs

> A comprehensive machine learning research project comparing Isolation Forest, One-Class SVM, and Autoencoder approaches for detecting insider threats and suspicious database access patterns.

[![Python 3.12.12]](https://www.python.org/downloads/)
[![TensorFlow 2.13.0]](https://tensorflow.org/)
[![License: MIT]](https://opensource.org/licenses/MIT)

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Research Methodology](#research-methodology)
- [Installation](#installation)
- [Results Export](#results-export)
- [License](#license)
- [Contact & Support](#contact--support)

---

## Overview

This research project addresses the critical challenge of **detecting anomalies in database access logs** to identify insider threats, privilege escalation, data exfiltration, and other malicious activities. The implementation follows academic publication standards with **zero data leakage**, **comprehensive evaluation metrics**, and **full reproducibility**.

### Research Objectives

1. **Generate realistic synthetic database access logs** with various anomaly patterns
2. **Implement and train three different anomaly detection models**
3. **Evaluate models using 15+ comprehensive metrics** (Precision, Recall, F1-Score, FPR, timing benchmarks)
4. **Compare strengths and weaknesses** of each approach
5. **Provide actionable recommendations** for real-world deployment
6. **Ensure full reproducibility** with fixed random seeds and documented dependencies

### Why This Matters

- **Database security breaches** cost organizations millions annually
- **Insider threats** account for 60%+ of security incidents
- **Traditional rule-based systems** fail to detect novel attack patterns
- **Machine learning** enables adaptive, data-driven anomaly detection

---

## Key Features

### Research Quality
- **Zero data leakage** - Temporal train-test split with chronological ordering
- **15+ evaluation metrics** - Detection accuracy, computational efficiency, statistical tests
- **Feature importance analysis** - Ablation study quantifying feature impact
- **Ensemble methods** - 4 hybrid strategies with statistical validation
- **Full reproducibility** - Fixed seeds (42), exported datasets, metadata

### Realistic Anomaly Patterns
1. **Unusual Access Times** - Queries at odd hours (2-5 AM)
2. **Privilege Escalation** - Normal users accessing admin tables
3. **Data Exfiltration** - Abnormally high data transfer (>50 MB)
4. **Rapid Query Bursts** - >100 queries in single session
5. **Unauthorized Table Access** - Accessing restricted tables
6. **Suspicious IP Changes** - Multiple IPs for same user

### Comprehensive Evaluation
- **Detection Performance**: Precision, Recall, F1-Score, Accuracy, FPR, TNR, ROC-AUC
- **Computational Efficiency**: Training time, inference time, throughput (samples/sec)
- **Statistical Validation**: McNemar's test, bootstrap confidence intervals, chi-square tests
- **Visual Analysis**: Confusion matrices, ROC curves, feature importance plots

### Production-Ready
- **Configurable thresholds** for different sensitivity requirements
- **Real-time inference benchmarks** for deployment planning
- **Ensemble strategies** for improved robustness
- **13 CSV exports** ready for integration with monitoring systems

---

## Research Methodology

### Dataset Generation
- **10,500 total records** (10,000 normal + 500 anomalous)
- **90-day simulation period** with realistic temporal patterns
- **50 unique users** across 3 roles (normal, analyst, admin)
- **6 database tables** with role-based access control
- **Temporal train-test split**: 80% training (Days 1-72) | 20% testing (Days 73-90)

### Feature Engineering (23 Features)
- **Temporal**: Hour of day, day of week, weekend indicator
- **User behavior**: Query frequency, session duration, data transferred
- **Statistical**: User-based Z-scores, historical averages
- **Categorical encoded**: User role, IP address, query type, table accessed

### Models Evaluated
1. **Isolation Forest** - Tree-based ensemble isolating outliers
2. **One-Class SVM** - Support vector machine defining normal boundaries
3. **Autoencoder** - Neural network reconstructing normal patterns

---

## Installation

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or Google Colab
- 4GB+ RAM recommended
- ~100MB disk space

### Dependencies

```
numpy==1.24.3
pandas==2.0.3
matplotlib==3.7.2
seaborn==0.12.2
scikit-learn==1.3.0
tensorflow==2.13.0
scipy==1.11.1
imbalanced-learn==0.11.0
```

---

## Results Export

All results are automatically exported to `research_exports/` in CSV format:

### Core Datasets
1. **01_synthetic_database_logs_RAW.csv** - Original generated dataset
2. **02_processed_features.csv** - Engineered features + labels
3. **03_model_predictions.csv** - Predictions from all 3 models

### Evaluation Results
4. **04_performance_metrics_complete.csv** - All metrics (detection + timing)
5. **05_confusion_matrices.csv** - TP, FP, TN, FN for each model
6. **06_feature_importance.csv** - Feature rankings
7. **07_feature_ablation_study.csv** - Feature removal impact
8. **08_ensemble_comparison.csv** - Hybrid strategies performance
9. **09_detection_by_anomaly_type.csv** - Per-pattern breakdown
10. **10_timing_benchmarks.csv** - Computational efficiency
11. **11_statistical_tests.csv** - McNemar's + Bootstrap results
12. **12_research_metadata.csv** - Experiment configuration

13. **README.txt** - Data dictionary

---

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### Permissions
Commercial use  
Modification  
Distribution  
Private use  

### Conditions
License and copyright notice must be included

---

## Contact & Support

- **Email**: 22068050@imail.sunway.edu.my
- **Email**: 22059240@imail.sunway.edu.my 
- **Email**: 24120016@imail.sunway.edu.my

---

*Last updated: December 28, 2025*