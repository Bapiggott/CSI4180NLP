# Integrating Explainable AI for Effective Malware Detection in Encrypted Network Traffic

## Overview
This study (Zeleke et al., 2025, *arXiv*) presents an explainable AI (XAI) framework for detecting malware in encrypted network traffic. The approach integrates multi-view feature extraction with ensemble models and emphasizes interpretability using SHAP.

**Key elements:**
- **Datasets:**
  - 1,127 encrypted malware connections across 54 malware families.
  - CTU-13 dataset for additional malicious and benign flows.
- **Features:**
  - Handshake information, certificate metadata, packet timing, statistical flow features, TLS versions and extensions.
- **Models:**
  - Random Forest, Extra Trees, and XGBoost.
  - XGBoost achieved ~99% accuracy, precision, and F1-score.
- **Explainability:**
  - SHAP values reveal both global and local feature importance.
  - Key signals include packet size distribution, inter-arrival times, TLS versions, and certificate validity.
- **Contribution:**
  - Combines strong malware detection with transparency, addressing trust and auditability.

## Relation to Our Project
Our project focuses on multimodal malware detection in encrypted traffic using NLP sequences and visual signatures.

**Direct connections:**
- Multi-view features overlap with our metadata and sequence design.
- SHAP-based interpretability can be applied to both NLP (sequence tokens) and vision (image regions) models in our system.
- Their methodology for combining multiple malware families is relevant for building diverse training sets.
- Balancing high detection performance with transparency directly supports our deployment goals.

## Possible Extensions
1. **Add Explainability:**  
   - Integrate SHAP for both sequence and vision branches.  
2. **Adopt Multi-View Features:**  
   - Incorporate certificate and TLS metadata into our multimodal pipeline.  
3. **Dataset Construction:**  
   - Merge multiple sources (e.g., CIC-IDS, CTU-13, N-BaIoT) to enrich malware diversity.  
4. **Hybrid Models:**  
   - Use interpretable models (e.g., XGBoost) as first-line filters before deep neural fusion models.  
5. **Adversarial Robustness:**  
   - Apply XAI to identify and defend against adversarial traffic manipulations.  

## Key Takeaways
- High accuracy and interpretability can coexist in malware detection.  
- SHAP highlights useful traffic features such as TLS versions and inter-arrival timing.  
- Our project should integrate explainability as a first-class objective.  
- Combining metadata with deep multimodal learning improves both detection and trustworthiness.
