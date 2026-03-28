# Neural Network — MNIST Digit Classification


---

## Project Overview

This project builds a **Feed-Forward Neural Network (MLP)** using TensorFlow/Keras to classify handwritten digit images into 10 categories (0–9). The model is trained from scratch using backpropagation, dropout regularization, and early stopping — achieving **97%+ accuracy** on 10,000 unseen test images.

This project demonstrates how deep learning can solve real-world image recognition problems without any pre-trained models.



##  Dataset

**MNIST — Handwritten Digit Classification**

| Detail | Info |
|--------|------|
| Source | Built into TensorFlow/Keras |
| Total Images | 70,000 grayscale images |
| Training Set | 60,000 images |
| Test Set | 10,000 images |
| Image Size | 28×28 pixels (784 inputs) |
| Classes | 10 (digits 0–9) |

---

## Project Structure

```
neural-network-mnist/
│
├── notebooks/
│   └── mnist_neural_network.ipynb   ← Full pipeline in one notebook
│
├── outputs/
│   ├── 0_sample_digits.png          ← Sample images from dataset
│   ├── 1_training_history.png       ← Accuracy & loss curves
│   ├── 2_predictions.png            ← Model predictions on test images
│   └── 3_confusion_matrix.png       ← Which digits get confused
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/vhogod/neural-network-mnist.git
cd neural-network-mnist
```

### 2. Install dependencies
```bash
pip install tensorflow numpy matplotlib seaborn scikit-learn
```

### 3. Open the notebook
```bash
jupyter notebook notebooks/mnist_neural_network.ipynb
```

Run all cells from top to bottom — dataset downloads automatically.



##  Neural Network Architecture

```
INPUT LAYER      784 neurons   ← one per pixel (28×28 flattened)
      ↓
HIDDEN LAYER 1   128 neurons   ← learns edges and basic shapes
      ↓  Dropout (20%)
HIDDEN LAYER 2    64 neurons   ← learns complex digit patterns
      ↓  Dropout (20%)
OUTPUT LAYER      10 neurons   ← one per digit (0–9), Softmax
```

| Layer | Type | Neurons | Activation |
|-------|------|---------|------------|
| Input | Dense | 784 | — |
| Hidden 1 | Dense + Dropout | 128 | ReLU |
| Hidden 2 | Dense + Dropout | 64 | ReLU |
| Output | Dense | 10 | Softmax |

**Total trainable parameters:** ~109,386

---

##  What the Notebook Does

| Section | Description |
|---------|-------------|
| **Data Loading** | Loads MNIST directly from Keras datasets |
| **Preprocessing** | Normalizes pixels (0–255 → 0–1), flattens images, one-hot encodes labels |
| **Model Building** | Defines MLP architecture with Dropout layers |
| **Training** | Trains with Adam optimizer, categorical crossentropy loss, early stopping |
| **Evaluation** | Computes accuracy and loss on 10,000 test images |
| **Visualization** | Saves 4 charts showing performance and predictions |



##  Model Results

| Metric | Value |
|--------|-------|
| **Test Accuracy** | **97%+** |
| Test Loss | < 0.10 |
| Epochs Trained | 15 |
| Batch Size | 128 |
| Optimizer | Adam |
| Loss Function | Categorical Crossentropy |

---

##  Visualizations

| Chart | What It Shows |
|-------|---------------|
| `0_sample_digits.png` | Sample handwritten digits from the dataset |
| `1_training_history.png` | Accuracy and loss curves across epochs |
| `2_predictions.png` | Model predictions vs true labels (green = correct, red = wrong) |
| `3_confusion_matrix.png` | Which digits the model confuses with each other |

---

##  Key Concepts Demonstrated

- **Backpropagation** — how the network adjusts weights after each prediction
- **Dropout Regularization** — randomly disabling neurons to prevent overfitting
- **Early Stopping** — halting training when validation loss stops improving
- **Softmax Activation** — converting raw scores to class probabilities
- **One-Hot Encoding** — converting integer labels to binary class vectors
- **ReLU Activation** — introducing non-linearity in hidden layers

---

##  Tools & Libraries

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| TensorFlow / Keras | Neural network framework |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Confusion matrix heatmap |
| scikit-learn | Evaluation metrics |
| Anaconda / Jupyter | Development environment |

---



[![GitHub](https://img.shields.io/badge/GitHub-vhogod-181717?style=flat&logo=github)](https://github.com/vhogod)
