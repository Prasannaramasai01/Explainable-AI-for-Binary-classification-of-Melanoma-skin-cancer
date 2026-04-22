# Explainable AI for Binary Classification of Melanoma Skin Cancer

## 1. Project Motivation
Early detection of Melanoma is critical, as it is the most aggressive form of skin cancer. This project addresses the "black box" nature of standard Deep Learning models by implementing **Explainable AI (XAI)**. The goal is to provide dermatologists with not just a prediction, but a visual justification for that prediction using clinical and visual evidence.

## 2. Research Objectives
* Develop a **Multimodal Deep Learning** model integrating dermoscopic images with patient metadata.
* Benchmarking performance across **ResNet-18, ResNet-50, and ResNet-101** architectures.
* Address significant **Class Imbalance** using ROC-AUC as the primary performance metric.
* Implement **Grad-CAM** to visualize the specific morphological features (like pigment networks) driving the diagnosis.

## 3. The Dataset
* **Source:** ISIC 2020 Challenge Dataset.
* **Content:** Over 33,000 images with clinical metadata (Age, Sex, Anatomical Site).
* **Processing:** Images resized to 224x224; metadata transformed via One-Hot Encoding.

## 4. Model Architecture: Multimodal ResNet-101
The system uses a 101-layer Residual Network backbone. The final fully connected layer is modified to fuse:
1.  **Visual Features:** 2048-dimensional vector from the CNN backbone.
2.  **Metadata Features:** Clinical context processed through a separate linear layer.
3.  **Classification:** A fused feature vector passed through a final MLP for binary classification.

## 5. Key Performance Metrics
| Metric | Value |
| :--- | :--- |
| **Best Model** | ResNet-101 |
| **Validation AUC** | **0.7898** |
| **Accuracy** | 92.97% |

*Note: While accuracy is high, AUC (0.7898) is the more reliable indicator of performance due to the sparse nature of positive Melanoma cases in the dataset.*

## 6. Project Structure
* `Ram sai FPR 24082641.pdf`: Comprehensive final project report.
* `PRASANNA_RAMA_SAI_CHEGONDI__REPORT_123.ipynb`: Full implementation script (Data Loading -> Training -> XAI).

## 7. Future Directions
* **Advanced Architectures:** Testing Vision Transformers (ViT) for better global feature extraction.
* **Segmentation:** Adding a U-Net stage to isolate the lesion from healthy skin.
* **Optimization:** Using Weighted Cross-Entropy or SMOTE to further improve sensitivity to the minority class.

---
**Author:** Prasanna Rama Sai Chegondi  
**MSc Data Science** | **University of Hertfordshire** **Student ID:** 24082641
