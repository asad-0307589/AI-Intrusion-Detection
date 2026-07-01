# NetGuardAI: Generative AI Network Intrusion Detection

![Python](https://img.shields.io/badge/python-3.12%2B-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=flat&logo=PyTorch&logoColor=white)
![Dataset](https://img.shields.io/badge/Dataset-CICIoT2023-brightgreen.svg)
![License](https://img.shields.io/badge/License-MIT-blue.svg)

**NetGuardAI** is a robust, research-grade pipeline developed for high-accuracy network intrusion detection. This project systematically tackles fundamental challenges in cyber security datasets—particularly the severe class imbalance—by leveraging Generative AI techniques to augment underrepresented attack classes.

## 🚀 Overview

The modern IoT landscape generates massive amounts of traffic, leading to large-scale, highly imbalanced datasets. Traditional Machine Learning methods often struggle with long-tailed distributions where rare cyber-attack classes are neglected.

NetGuardAI presents a twofold approach:
1. **Base Implementation (`AE + LSTM + CNN`):** A parallel Autoencoder and LSTM pipeline fed into a Convolutional Neural Network, incorporating SMOTE to baseline the highly imbalanced CICIoT2023 dataset.
2. **Improved Proposed Model (`QA-CVAE + Attention`):** A sophisticated Generative AI architecture leveraging Quality-Aware Conditional Variational Autoencoders (QA-CVAE) with an attention mechanism to intelligently synthesize realistic minority class attack samples, significantly boosting Macro F1-score and rare attack class detection over the baseline.

## 👥 Contributors

This research project was collaboratively developed by:
- [asad-0307589](https://github.com/asad-0307589)
- [Abdullah2073](https://github.com/Abdullah2073)

## 📁 Repository Structure

```text
📦 NetGuardAI
 ┣ 📜 Report.pdf                                 # Comprehensive research paper and findings
 ┣ 📜 base-paper-implementation.ipynb            # Baseline model (AE + LSTM + CNN w/ SMOTE)
 ┣ 📜 improved-model-qa-cvae-attention.ipynb     # Enhanced Model (QA-CVAE + Attention)
 ┗ 📜 README.md                                  # Project documentation
```

## 🧠 Architecture Highlights

### The Data Challenge
The **CICIoT2023** dataset contains over 30 distinct attack types across 7 main classes (e.g., DDoS, DoS, Mirai, Recon, Spoofing, Web Attack). Due to high imbalance, rare scenarios (like Web Attacks) typically yield low detection rates.

### The Improved Solution: QA-CVAE + Attention
- **Quality-Aware CVAE:** Synthesizes high-fidelity simulated traffic flows specifically conditioning on the minority labels.
- **Attention Mechanism:** Automatically ranks feature importance, enabling the classifier to focus on the temporal characteristics of complex attack payloads.
- **Deeper Representation:** Merges latent representations with spatial features resulting in state-of-the-art anomaly detection benchmarks.

## 🛠️ How to Run

These notebooks are designed to be run directly in Google Colab or Kaggle (leveraging T4 GPUs). 

1. **Clone the repository:**
   ```bash
   git clone https://github.com/asad-0307589/NetGuardAI-Intrusion-Detection.git
   cd NetGuardAI-Intrusion-Detection
   ```

2. **Setup your environment:**
   Please ensure you have Python 3.10+ installed. Install the necessary dependencies:
   ```bash
   pip install torch pandas numpy matplotlib seaborn scikit-learn imbalanced-learn
   ```

3. **Running the Notebooks:**
   Open `jupyter notebook` in your terminal or upload the `.ipynb` files to Google Colab. The notebooks include automatic dependency installations for the containerized environment. Ensure Kaggle/Drive dataset paths are correctly set.

## 📈 Results and Findings

A full comparative analysis detailing baseline vs. improved precision-recall curves, confusion matrices, and Macro F1-score gains is available in the `Report.pdf`. The Generative AI approach yielded a measurable improvement in capturing rare attack classes compared to the traditional baseline.

## ⚖️ License
This project is licensed under the MIT License - see the LICENSE file for details.
