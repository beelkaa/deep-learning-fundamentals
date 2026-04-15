# 🧠 Deep Learning Fundamentals with PyTorch

A hands-on collection of notebooks covering core deep learning concepts — built from scratch using PyTorch, trained on MNIST.

---

## 📁 Repository Structure

```
deep-learning-fundamentals/
│
├── notebooks/
│   ├── 01_mlp_pytorch.ipynb
│   ├── 02_cnn_pytorch.ipynb
│   ├── 03_overfitting_underfitting.ipynb
│   └── 04_gradient_problems.ipynb
│
├── requirements.txt
└── README.md
```

---

## 📓 Notebooks

### 01 — Multilayer Perceptron (MLP)
**File:** `notebooks/01_mlp_pytorch.ipynb`

Covers the building blocks of neural networks from the ground up.

| Topic | What you'll learn |
|---|---|
| Neurons & Perceptrons | Weights, biases, activation functions |
| MLP Architecture | Input → Hidden → Output layers |
| Forward Pass | How data flows through the network |
| Backpropagation | Chain rule, gradient computation |
| Optimization | SGD, loss functions, one training step |

---

### 02 — Convolutional Neural Networks (CNN)
**File:** `notebooks/02_cnn_pytorch.ipynb`

Builds a CNN for image classification and trains it on MNIST (~99% accuracy).

| Topic | What you'll learn |
|---|---|
| Convolution | Filters, kernel size, stride, padding |
| Pooling | MaxPool, translation invariance |
| Batch Normalization | Why and when to use it |
| Full CNN Pipeline | Architecture → Training → Evaluation → Inference |

**Architecture:**
```
Input (1×28×28) → Conv1+ReLU+Pool → Conv2+ReLU+Pool → FC(128)+Dropout → FC(10)
```

---

### 03 — Overfitting & Underfitting
**File:** `notebooks/03_overfitting_underfitting.ipynb`

Demonstrates the bias-variance tradeoff visually and shows how to fix both problems.

| Experiment | Setup | Fix |
|---|---|---|
| Underfitting | 5-neuron bottleneck layer | Increase model capacity |
| Overfitting | Large model + tiny dataset (6k samples) | Regularization |
| Fix: Dropout | `nn.Dropout(p=0.5)` | Randomly zeroes neurons during training |
| Fix: L2 Weight Decay | `weight_decay=1e-4` in Adam | Penalizes large weights |

---

### 04 — Vanishing & Exploding Gradients
**File:** `notebooks/04_gradient_problems.ipynb`

Diagnoses the two most common training failures in deep networks and compares every fix side by side.

| Problem | Cause | Fix demonstrated |
|---|---|---|
| Vanishing Gradient | Sigmoid + deep network + random init | He initialization + ReLU |
| Exploding Gradient | Large weight init + high LR | Gradient clipping (`clip_grad_norm_`) |
| Both | — | Batch Normalization |

Includes **gradient norm visualizations** per layer to see the problem directly.

---

## ⚙️ Setup

### Prerequisites
- Python 3.8+
- pip

### Installation

```bash
# Clone the repo
git clone https://github.com/beelkaa/deep-learning-fundamentals.git
cd deep-learning-fundamentals

# Install dependencies
pip install -r requirements.txt
```

### Running the Notebooks

```bash
jupyter notebook notebooks/
```

Or open them directly in **VS Code** with the Jupyter extension.

> **Note:** MNIST data (~11 MB) is downloaded automatically on first run via `torchvision.datasets.MNIST`.

---

## 📦 Requirements

```
torch>=2.0.0
torchvision>=0.15.0
matplotlib>=3.7.0
numpy>=1.24.0
jupyter>=1.0.0
```

Save this as `requirements.txt` in your repo root.

---

## 🗺️ Learning Path

If you're new to deep learning, go through the notebooks in order:

```
MLP → CNN → Overfitting/Underfitting → Gradient Problems
```

Each notebook is self-contained and runnable top-to-bottom.

---

## 📊 Results Summary

| Model | Dataset | Test Accuracy |
|---|---|---|
| SmallCNN | MNIST | ~99% |
| UnderfitModel (5 neurons) | MNIST | ~90% |
| OverfitModel (no reg) | MNIST (10% subset) | Lower generalization |
| RegularizedModel (Dropout + L2) | MNIST (10% subset) | Better generalization |

---

## 🤝 Contributing

Pull requests are welcome. For major changes, open an issue first.

---

## 📄 License

MIT
