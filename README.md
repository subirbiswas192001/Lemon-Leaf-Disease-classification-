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

## Lemon Foliar Disease Classification Using Deep Learning and Attention-Based Feature Fusion

This repository contains the official implementation of the proposed **Hybrid Multi-Branch Attention Fusion Network (HMAF-Net)** for lemon leaf disease classification. The framework integrates a DenseNet121 backbone with multiple convolutional branches and attention-based feature fusion to improve feature representation and classification performance.

The proposed model was developed for automated citrus leaf pathology analysis and evaluated on the newly introduced **Citrus Leaf Pathology Multi-Class Image Dataset (CLP-14)**.

---

## ✨ Research Highlights

- Comprehensive review of lemon foliar disease detection research from 2017–2026.
- Introduction of a publicly available multi-class citrus leaf disease dataset.
- Development of a novel Hybrid Multi-Branch Attention Fusion Network (HMAF-Net).
- Integration of:
  - DenseNet121 backbone
  - Standard Conv2D branch
  - Depthwise convolution branch
  - Separable convolution branch
  - Channel attention (SE block)
  - Branch attention-based feature fusion
- Classification using a Random Forest (RF) classifier.
- Extensive ablation and comparative experiments.

---

## 🧠 Proposed Architecture

The proposed HMAF-Net architecture combines deep feature extraction and attention-based fusion mechanisms.

### Main Components

1. **DenseNet121 Backbone**
   - Pre-trained on ImageNet.
   - Used as the primary feature extractor.

2. **Multi-Branch Feature Extraction**
   - Standard Conv2D branch
   - DepthwiseConv2D branch
   - SeparableConv2D branch

3. **Attention Mechanisms**
   - Squeeze-and-Excitation (SE) channel attention
   - Branch attention fusion

4. **Classification Layer**
   - Random Forest (RF) classifier for final classification.

---

## 📂 Dataset Information

### Citrus Leaf Pathology Multi-Class Image Dataset (CLP-14)

The proposed dataset contains:

- **4,247 high-resolution citrus leaf images**
- **14 disease classes**
- Real-world field images collected from lemon gardens
- Original and augmented datasets

### Dataset Structure

```text
Dataset/
│
├── Train/
├── Validation/
└── Test/
```

### Data Split

| Split | Percentage |
|------|------|
| Training | 80% |
| Validation | 10% |
| Testing | 10% |

---

## 📊 Experimental Results

The proposed model achieved strong performance on both the proposed dataset and external benchmark datasets.

| Dataset | Accuracy |
|------|------|
| CLP-14 | 96% |
| Dataset-2 | 100% |
| Dataset-3 | 97% |

These results demonstrate the effectiveness and robustness of the proposed HMAF-Net framework.

---

## 📁 Repository Structure

```text
HMAF-Net/
│
├── dataset/
├── models/
├── notebooks/
├── results/
├── figures/
├── saved_models/
├── requirements.txt
├── train.py
├── evaluate.py
├── inference.py
└── README.md
```

---

## ⚙️ Installation

### Clone Repository

```bash
git clone https://github.com/your-username/HMAF-Net.git
cd HMAF-Net
```

### Create Environment

```bash
python -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 📦 Requirements

Main libraries used in this project:

```text
TensorFlow
Keras
NumPy
Scikit-learn
XGBoost
Matplotlib
Pandas
OpenCV
```

---

## 🚀 Model Training

Run the following command to train the model:

```bash
python train.py
```

---

## 📈 Model Evaluation

```bash
python evaluate.py
```

Evaluation metrics include:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC-AUC Score

---

## 🔍 Inference

To test a single image:

```bash
python inference.py --image path_to_image
```

---

## 🧪 Ablation Study

Several experiments were conducted to analyze the contribution of:

- DenseNet121 backbone
- Multi-branch feature extraction
- Channel attention
- Branch attention fusion
- Random Forest classifier

---

## 🌱 Applications

The proposed framework can be used for:

- Automated plant disease diagnosis
- Precision agriculture
- Smart farming systems
- Mobile-based agricultural applications
- Real-time crop health monitoring

---

## ⚠️ Limitations

- Increased computational complexity due to attention mechanisms and multi-branch architecture.
- Dependence only on visual leaf features without environmental information.

---

## 🔮 Future Work

Future research directions include:

- Expanding dataset diversity using images from multiple geographic regions.
- Integration of multi-modal agricultural data such as temperature and humidity.
- Real-time deployment on smart devices and edge systems.
- Explainable AI (XAI) integration for improved interpretability.
- Large-scale field validation with agricultural experts.

---

## 📚 Citation

If you use this work in your research, please cite:

```bibtex
@article{HMAFNet2026,
  title={Hybrid Multi-Branch Attention Fusion Network for Lemon Foliar Disease Classification},
  author={Author Name},
  journal={Journal Name},
  year={2026}
}
```

---

## 📜 License

This project is released under the MIT License.

---

## 🙏 Acknowledgements

We acknowledge the support of researchers, agricultural experts, and contributors involved in dataset collection and experimental validation.

---

## 📧 Contact

For questions, collaborations, or research discussions:

- Name: Subir Biswas
- Research Area: Machine Learning, Computer Vision, Agricultural AI
- Email: your-email@example.com
- GitHub: https://github.com/your-username

---

## ⭐ Star This Repository

If you find this work useful for your research, please consider giving this repository a star.

