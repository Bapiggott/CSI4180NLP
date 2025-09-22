# MFF: A Multimodal Feature Fusion Approach for Encrypted Traffic Classification

## Overview
This study (Huang et al., 2025, *Electronics*) proposes **MFF (Multimodal Feature Fusion)**, a deep learning framework for classifying encrypted traffic. It addresses the limitations of sequence truncation in existing methods by combining both temporal and statistical features.

**Key elements:**
- **Datasets:**
  - ISCX VPN-nonVPN (12 classes used).
  - USTC-TFC (20 classes: 10 benign, 10 malware families).
- **Model Design:**
  - **Temporal branch:** SE-ResNet18 (1D ResNet18 with Squeeze-and-Excitation attention) to capture sequential burst patterns and dependencies.
  - **Statistical branch:** Autoencoder (AE) to compress and reconstruct 52 handcrafted features (e.g., packet length, entropy, TLS records).
  - **Fusion module:** Concatenates embeddings from both branches and classifies via fully connected layers.
- **Interpretability:**
  - SHAP analysis highlights which temporal and statistical features influence predictions.
- **Results:**
  - ISCX VPN-nonVPN: 99.61% accuracy.
  - USTC-TFC: 99.99% accuracy.
  - Outperforms DeepPacket, ET-BERT, LAMBERT, Flow-GNN, and NetMamba.
- **Contribution:**
  - Demonstrates that combining temporal and statistical modalities mitigates feature loss and significantly improves accuracy.

## Relation to Our Project
Our project focuses on multimodal malware detection in encrypted traffic using NLP (sequential metadata) and visual signatures (flow images).  

**Direct connections:**
- Their **temporal features** align with our NLP-based sequence modeling of traffic metadata.
- Their **statistical features** parallel our numeric flow-level features, which we can incorporate into a multimodal pipeline.
- The fusion design (temporal + statistical) directly supports our idea of fusing NLP and vision modalities.
- The use of **SHAP for interpretability** validates our plan to integrate transparency into evaluation.

## Possible Extensions
1. **Adopt Dual-Branch Fusion:**  
   - Implement a dual-path architecture where NLP handles sequences and CNN/ViT handles images.  
2. **Statistical Feature Integration:**  
   - Add handcrafted statistical features as a third modality in addition to NLP and vision.  
3. **Feature Reduction with Autoencoders:**  
   - Use autoencoders to compress statistical traffic features before fusion.  
4. **Interpretability:**  
   - Extend SHAP to multimodal fusion, showing which sequence tokens or image regions drive results.  
5. **Lightweight Deployment:**  
   - Adapt SE-ResNet18 + AE design for real-time IDS use in constrained environments.

## Key Takeaways
- Multimodal fusion significantly boosts performance over unimodal approaches.  
- Combining handcrafted features with learned embeddings reduces feature loss.  
- SHAP provides interpretability and strengthens trust in results.  
- The paper confirms the value of fusion-based architectures for encrypted traffic classification, supporting our project’s design choices.
