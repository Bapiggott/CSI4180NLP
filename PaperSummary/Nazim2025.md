# Multimodal Malware Classification using Ensemble Deep Neural Network Framework

## Overview
This study (Nazim et al., 2025, *Scientific Reports*) proposes a multimodal malware analysis framework that integrates malware images (byteplot visualizations of binaries) with numeric features (behavioral and network statistics) for effective malware detection.  

**Key elements:**
- **Datasets:**
  - CCCS-CIC-AndMal-2020 (numeric Android malware features).
  - Malimg and Malevis datasets (grayscale and RGB malware images).
- **Data Preprocessing:**
  - Feature reduction with Neighbourhood Component Analysis (NCA).
  - Class imbalance handled with SMOTE oversampling.
- **Models:**
  - Ensemble CNN+LSTM (24 layers) for imagery.
  - RUSBoost for numeric features (undersampling + boosting).
  - Predictions combined with late fusion (majority vote, bagging, stacking).
- **Results:**
  - Imagery model: ~96% accuracy.
  - Numeric model: ~91% accuracy.
  - Multimodal late fusion: 95.36% accuracy, with improved recall and robustness.
- **Contribution:**
  - Demonstrates that numeric + visual fusion outperforms unimodal approaches, especially for evolving malware families.

## Relation to Our Project
Our project focuses on multimodal detection of malware in encrypted traffic using NLP for sequential metadata and visual signatures (flow images and heatmaps).  

**Direct connections:**
- Numeric malware features align with our traffic metadata (packet sizes, timing, flags).
- Malware byteplot images parallel our packet-flow heatmaps and entropy visualizations.
- Late fusion in their framework validates our plan to test early fusion, late fusion, and cross-attention.
- Their handling of class imbalance (SMOTE + RUSBoost) applies directly to traffic datasets like CIC-IDS2017 and N-BaIoT.

## Possible Extensions
1. **Adopt Ensemble + Late Fusion:**  
   - Apply RUSBoost or similar ensemble learners to NLP features.  
   - Test meta-learners (stacking) to integrate CNN/ViT (images) with Transformer/LSTM (sequences).  
2. **Balance and Select Features:**  
   - Use SMOTE for minority malicious flows.  
   - Apply NCA or PCA to reduce traffic feature dimensionality.  
3. **Cross-Modal Consistency:**  
   - Study how traffic visualizations align with metadata anomalies.  
4. **Interpretability:**  
   - Add SHAP or LIME for transparency across both modalities.  
5. **Cross-Domain Testing:**  
   - Combine IoT datasets (N-BaIoT) with enterprise datasets (CIC-IDS) to test robustness.

## Key Takeaways
- Multimodal analysis consistently beats unimodal baselines.  
- Ensemble and late fusion improve robustness in imbalanced scenarios.  
- Visual and numeric/sequence modalities capture complementary perspectives.  
- Supports our hypothesis: fusing NLP and vision yields stronger encrypted malware detection.
