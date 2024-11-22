# COVID-19 Detection Using Chest CT Scans with BYOL

This project applies **Bootstrap Your Own Latent (BYOL)**, a self-supervised learning framework, to detect COVID-19 from chest CT scans. BYOL enables robust feature representation learning without requiring labeled data, making it highly effective for medical imaging tasks with limited labeled datasets.

## 🚀 Project Overview
The aim of this project is to leverage BYOL for pre-training on chest CT scan images and fine-tune the learned representations for the classification of scans into **COVID-19** and **non-COVID-19** categories. 

### Key Features:
- **Self-Supervised Pre-Training**: Leveraged BYOL to pre-train the model on unlabeled CT scans.
- **Fine-Tuning**: Fine-tuned the pre-trained model on a balanced labeled dataset for COVID-19 classification.
- **High Performance**: Achieved an accuracy of approximately **80%**, with similar precision and recall scores on the test set.

## 📊 Results
| Metric           | Score  |
|-------------------|--------|
| **Accuracy**      | 80%    |
| **Precision**     | ~80%   |
| **Recall**        | ~80%   |

## 📂 Dataset
- **Dataset Description**: The dataset consists of chest CT scans, balanced with **1,200 images** for each class: COVID-19 and non-COVID-19.
- **Preprocessing**: All images were resized to **224x224 pixels** to maintain uniformity and optimize model performance.

## 🛠️ Model Overview
### **Bootstrap Your Own Latent (BYOL)**
BYOL is a self-supervised learning framework designed to learn meaningful feature representations without requiring labeled data. It consists of:
1. **Online Network**: A trainable encoder that extracts features from input images.
2. **Target Network**: A stabilized copy of the online network, updated using an exponential moving average (EMA) of the online network’s weights.

The two networks interact through:
- **Latent Space Matching**: BYOL minimizes the difference between the online network's predictions and the target network's representations, encouraging effective learning.

### Fine-Tuning
After pre-training with BYOL, the learned representations were fine-tuned using a labeled dataset to classify images as COVID-19 or non-COVID-19.

## 📈 Training Workflow
1. **Pre-Training**:
   - Pre-trained the BYOL model on unlabeled CT scans.
   - Focused on extracting generalized features relevant to chest CT scan images.
2. **Fine-Tuning**:
   - Fine-tuned the model using supervised learning on a labeled dataset.
   - Optimized for binary classification (COVID-19 vs. non-COVID-19).

## 📜 Requirements
To reproduce the results, ensure the following dependencies are installed:
- Python 3.8+
- PyTorch 1.10+
- torchvision
- numpy
- pandas
- matplotlib
