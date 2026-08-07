# 🍋 Hybrid Multi-Branch Attention Fusion Network (HMAF-Net)

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-DeepLearning-orange)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Research-red)
[![Dataset](https://img.shields.io/badge/Dataset-Download-blue?logo=google-drive)](https://www.kaggle.com/datasets/chayanmondalabir/citrus-leaf-pathology-multi-class-image-dataset)

### Deep Learning Framework for Citrus Leaf Disease Classification

<img src="assets/lemon leaf disease.jpg" alt="Lemon Leaf Disease Dataset" width="700">

</div>


**HMAF-Net: Hybrid Multi-Branch Attention Fusion Network for Lemon Foliar Disease Classification**

This repository contains the official implementation and supplementary resources for the proposed **Hybrid Multi-Branch Attention Fusion Network (HMAF-Net)** for lemon(citrus) leaf disease classification.

HMAF-Net integrates a **DenseNet121 backbone**, multiple convolutional feature-extraction branches, **Squeeze-and-Excitation (SE) channel attention**, and **branch-level attention-based feature fusion** to learn complementary and discriminative representations for multi-class citrus leaf disease classification.

The proposed framework was developed and evaluated using the **Citrus Leaf Pathology Multi-Class Image Dataset (CLP-14)** and further validated on three independent external datasets to assess cross-dataset generalization.

---

## ✨ Research Highlights

- Comprehensive review of lemon foliar disease detection research from **2017–2026**.
- Introduction of the **Citrus Leaf Pathology Multi-Class Image Dataset (CLP-14)** containing 14 disease classes.
- Development of the **Hybrid Multi-Branch Attention Fusion Network (HMAF-Net)**.
- Integration of:
  - DenseNet121 backbone
  - Standard Conv2D branch
  - Depthwise convolution branch
  - Separable convolution branch
  - Squeeze-and-Excitation (SE) channel attention
  - Branch-level attention-based feature fusion
- Comparison with conventional CNN and transformer-based deep learning architectures.
- Evaluation using multiple classification metrics.
- Ablation experiments to investigate the contribution of major architectural components.
- External validation using three independent datasets.
- Computational complexity analysis including parameters, FLOPs, model size, inference latency, and throughput.
- Explainability analysis using GradCAM++, Vanilla Gradients, Integrated Gradients, and SmoothGrad

---

## 🧠 Proposed HMAF-Net Architecture

The proposed HMAF-Net combines deep feature extraction with multi-branch attention-based feature fusion.

### Main Components

#### 1. DenseNet121 Backbone

- Pre-trained on ImageNet.
- Used as the primary deep feature extractor.
- Provides rich hierarchical representations of citrus leaf images.

#### 2. Multi-Branch Feature Extraction

The framework employs complementary convolutional branches to capture different characteristics of disease-related visual patterns:

- **Standard Conv2D branch**
- **Depthwise convolution branch**
- **Separable convolution branch**

These branches are designed to provide complementary feature representations while maintaining computational efficiency.

#### 3. Attention Mechanisms

HMAF-Net incorporates two levels of attention:

- **Squeeze-and-Excitation (SE) channel attention**
- **Branch-level attention-based feature fusion**

The attention mechanisms emphasize informative feature channels and branches before the final classification stage.

#### 4. Classification

The extracted and fused representations are used for disease classification. The experimental framework also evaluates different downstream classifiers, including:

- Neural Network (NN)
- Random Forest (RF)
- XGBoost

---

# 📂 Dataset Information

## 🍃 Citrus Leaf Pathology Multi-Class Image Dataset (CLP-14)

The proposed **CLP-14** dataset contains:

- **4,247 original citrus leaf images**
- **14 classes**
- Healthy and diseased citrus leaf samples
- Images collected from multiple sources and lemon-growing environments
- Original and augmented versions used for experimental analysis

The dataset covers a broad range of citrus leaf disease categories and is intended to support multi-class citrus leaf pathology research.

### Dataset Classes

The CLP-14 dataset contains **14 classes**, including:

1. Anthracnose
2. Bacterial Blight
3. Black Spot
4. Citrus Canker
5. Citrus Mite
6. Curl Leaf
7. Curl Virus
8. Deficiency Leaf
9. Dry Leaf
10. Greening
11. Healthy Leaf
12. Melanose
13. Sooty Mould
14. Spider Mites

---

## 📊 Dataset Distribution

The class-wise distribution of the CLP-14 dataset is provided in the manuscript in:

**Table 3. Class Distribution in the Citrus Leaf Pathology Multi-Class Image Dataset**

The repository will contain the corresponding dataset information and experimental files.

---

## 📁 Dataset Structure

```text
CLP-14/
│
├── Train/
├── Validation/
└── Test/
```

---

## 📌 Data Split

The experimental dataset follows the following split:

| Split | Percentage |
|---|---:|
| Training | 70% |
| Validation | 15% |
| Testing | 15% |

**Important:** Data augmentation is applied to the training data only after the dataset split to maintain separation between training, validation, and test samples.

---

# 🔗 CLP-14 Dataset

The proposed **CLP-14 and CLP-14-Aug** datasets are available through Kaggle:

**Dataset:**  
https://www.kaggle.com/datasets/chayanmondalabir/citrus-leaf-pathology-multi-class-image-dataset

---

# 🌍 External Dataset Validation

To further evaluate the generalization capability of HMAF-Net, the proposed model was tested on three independent external datasets.

## 📊 Experimental Results

| Dataset | Name | Total Images | Number of Classes | HMAF-Net Accuracy |
|---|---|---:|---:|---:|
| **Dataset-1** | Smartphone Image Dataset for Aegle Marmelos, Hog Plum and Lemon Plant Leaf | 1,232 | 4 | **97.48%** |
| **Dataset-2** | A Citrus Fruits and Leaves Dataset for Detection and Classification of Citrus Diseases through Machine Learning | 609 | 5 | **95.89%** |
| **Dataset-3** | Comprehensive Lemon Leaf Disease Dataset for Advanced Detection and Sustainable Agriculture | 1,354 | 9 | **98.23%** |

These experiments demonstrate that HMAF-Net maintains strong classification performance across external datasets containing different numbers of classes and image distributions.

---

## 🔗 External Dataset Sources

### Dataset-1

**Smartphone Image Dataset for Aegle Marmelos, Hog Plum and Lemon Plant Leaf**

- Total images: **1,232**
- Number of classes: **4**
- Dataset: https://data.mendeley.com/datasets/54r883j5zr/1

### Dataset-2

**A Citrus Fruits and Leaves Dataset for Detection and Classification of Citrus Diseases through Machine Learning**

- Total images: **609**
- Number of classes: **5**
- Dataset: https://data.mendeley.com/datasets/3f83gxmv57/2

### Dataset-3

**Comprehensive Lemon Leaf Disease Dataset for Advanced Detection and Sustainable Agriculture**

- Total images: **1,354**
- Number of classes: **9**
- Dataset: https://data.mendeley.com/datasets/44nrn4593f/1

---

# 📈 Model Evaluation

The proposed HMAF-Net was evaluated using multiple classification and statistical metrics, including:

- Accuracy
- Precision
- Recall
- F1-score
- Matthews Correlation Coefficient (MCC)
- ROC-AUC
- Confusion Matrix
- Per-class performance
- Macro-averaged performance

---

# ⚙️ Computational Complexity

The computational characteristics of HMAF-Net were evaluated in terms of model size, parameter count, computational cost, and inference efficiency.

| Metric | Value |
|---|---:|
| Total Parameters | **7,489,701** |
| Trainable Parameters | **7,406,053** |
| Non-trainable Parameters | **83,648** |
| Model Size | **28.57 MB** |
| Computational Cost | **5.81 GFLOPs** |
| FLOPs | **5,809,803,614** |
| Average Inference Latency | **12.769 ms/image** |
| Inference Throughput | **78.31 FPS** |

These measurements provide an assessment of the computational requirements and inference efficiency of the proposed architecture.

---

# 🧪 Ablation Study

Ablation experiments were conducted to investigate the contribution of the major components of HMAF-Net.

The experiments examine the effects of:

- DenseNet121 backbone
- Standard convolution branch
- Depthwise convolution branch
- Separable convolution branch
- Channel attention (SE block)
- Branch attention fusion
- Classifier configuration
- Data augmentation

The complete ablation results and corresponding experimental outputs will be provided in the repository.

---

# 🤖 Comparison with Deep Learning Architectures

HMAF-Net was compared with several established deep learning architectures to evaluate its classification performance.

The comparative experiments include conventional CNN-based models and transformer-based architectures.

A **Vision Transformer (ViT)** model, `vit_base_patch16_224`, was also evaluated as a representative transformer-based architecture.

The comparative results are reported in the manuscript in:

**Table 13. Performance Comparison of Various Deep Learning Architectures for Disease Classification on Augmented Data.**

---

# 📊 Cross-Dataset Evaluation

HMAF-Net was evaluated on:

- Proposed **CLP-14** dataset
- Proposed **CLP-14-Aug** dataset
- External **Dataset-1**
- External **Dataset-2**
- External **Dataset-3**

This evaluation was conducted to assess the consistency of the proposed framework across datasets with different class configurations and image distributions.

---

# 📁 Repository Structure

```text
HMAF-Net/
│
├── Assets/
│
├── models/
│
├── notebooks/
│
├── results/
│   ├── results/
│   └── Ablation/
│
├── figures/
│
├── requirements.txt
│
└── README.md
```

> **Note:** Additional source files, trained models, experimental results, and supplementary materials will be uploaded to this repository upon publication of the associated research article.

---

# ⚙️ Installation

## Clone Repository

```bash
git clone https://github.com/subirbiswas192001/Lemon-Leaf-Disease-classification-.git
cd Lemon-Leaf-Disease-classification-
```

## Create a Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Requirements

The complete environment and package versions will be provided in `requirements.txt`.

---

# 📈 Evaluation

After installation, the trained model can be evaluated using:

```bash
python evaluate.py
```

The evaluation pipeline provides:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- MCC
- Confusion Matrix
- Per-class performance

---

# 🔬 Reproducibility

To improve reproducibility, the experimental setup includes documentation of:

- Hardware configuration
- GPU specifications
- Software environment
- Python version
- Deep learning framework versions
- Random seed
- Dataset split
- Training configuration
- Model parameters
- Evaluation protocols

The corresponding configuration details are provided in the manuscript and repository files.

---

# 🌱 Potential Applications

The current study is based primarily on experimental and dataset-based evaluation and **does not constitute a complete real-field deployment system**.

Nevertheless, the proposed framework may provide a foundation for future applications in:

- Automated plant disease diagnosis
- Precision agriculture
- Smart farming systems
- Agricultural decision-support systems
- Mobile-based plant disease identification
- Edge-based agricultural monitoring

Real-world deployment requires additional validation under diverse field conditions.

---

# ⚠️ Limitations

The current study has several limitations:

- Performance may be affected by variations in illumination, background complexity, occlusion, camera distance, and image quality.
- Early-stage disease symptoms may be difficult to identify from visual features alone.
- Generalization across different citrus varieties, geographic regions, and environmental conditions requires further investigation.
- The multi-branch attention architecture introduces additional computational requirements compared with simpler CNN models.
- Environmental variables such as temperature, humidity, and soil conditions are not incorporated into the current visual classification framework.

---

# 🔮 Future Work

Future research will focus on improving the robustness, interpretability, and practical applicability of HMAF-Net.

Planned directions include:

- Expanding the dataset using images from multiple geographic regions.
- Collecting larger-scale field-acquired images under diverse environmental conditions.
- Evaluating robustness under varying illumination and complex backgrounds.
- Addressing occlusion and different camera distances.
- Investigating early-stage disease symptoms.
- Investigating multiple simultaneous disease infections.
- Integrating multi-modal agricultural information such as temperature and humidity.
- Optimizing the architecture for mobile and edge computing platforms.
- Conducting large-scale field validation with agricultural experts.

---

# 📚 Citation

If you use this work, dataset, or implementation in your research, please cite the associated publication:

```bibtex
@article{HMAFNet2026,
  title={Hybrid Multi-Branch Attention Fusion Network for Lemon Foliar Disease Classification},
  author={Biswas, Subir and Mondal, Abir},
  journal={----},
  year={2026}
}
```

> **Note:** The journal name, volume, issue, pages, and DOI will be updated after publication.

---

# 📜 License

This project is released under the **MIT License**.

---

# 🙏 Acknowledgements

We acknowledge the researchers, agricultural experts, dataset contributors, and collaborators who supported the development, dataset preparation, and experimental evaluation of this research.

Special thanks to **Abir Mondal** for his valuable contribution, dedication, research support, and commitment throughout this work.

---

# 📧 Contact

## Subir Biswas

- **Research Area:** Healthcare AI , Signal Analysis, Smart System 
- **Email:** subirbiswas192001@gmail.com
- **Website:** https://subirbiswas192001.github.io/subir-web/
- **LinkedIn:** https://www.linkedin.com/in/subir-biswas-engineer/
- **Kaggle:** https://www.kaggle.com/subirbiswas19

## Abir Mondal

- **Research Area:** Machine Learning, Computer Vision, Agricultural AI
- **Email:** chayanm4565@gmail.com
- **LinkedIn:** https://www.linkedin.com/in/chayanmondalabir/
- **Kaggle:** https://www.kaggle.com/chayanmondalabir

---

# ⭐ Star This Repository

If you find this work useful for your research, please consider giving this repository a ⭐ **star** and sharing it with other researchers working in agricultural AI, computer vision, and plant disease classification.
