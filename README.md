# Empirical Analysis of Vanishing Gradients in Deep Neural Networks

## 🚀 Overview
This project demonstrates and experimentally validates the **vanishing gradient problem** in deep neural networks using PyTorch, and compares it with a stable architecture that mitigates the issue.

The study highlights how activation functions, initialization strategies, and loss design impact gradient flow and learning dynamics.

---

## 🧠 Problem Statement
Deep neural networks often suffer from **vanishing gradients**, where gradients shrink exponentially as they propagate backward through layers.

This leads to:
- Slow or no learning in early layers
- Poor convergence
- Inefficient deep representations

---

## 🧪 Experiment Setup

We compare two pipelines:

### ❌ Vanishing Gradient Model
- Activation: Sigmoid (all layers)
- Output: Sigmoid
- Loss: BCELoss
- Optimizer: SGD
- Initialization: Default

### ✅ Stable Model
- Activation: ReLU
- Output: Linear
- Loss: BCEWithLogitsLoss
- Optimizer: Adam
- Initialization: He (Kaiming)
- Input: Standardized

---

## 🏗️ Architecture
- Input → 128 → 64 → 32 → 16 → 8 → 1

---

## 📊 Key Results

### Gradient Flow (Sigmoid Network)

| Layer | Gradient Norm |
|------|--------------|
| L1   | ~1e-6 |
| L2   | ~1e-6 |
| L3   | ~1e-5 |
| L4   | ~1e-4 |
| L5   | ~1e-3 |
| Output | ~1e-2 |

👉 Clear **exponential decay of gradients**

---

### Training Behavior

- Sigmoid Model:
  - Unstable loss
  - Slow convergence

- Stable Model:
  - Smooth loss decrease
  - Faster learning

---

## ⚙️ Installation

```bash
git clone https://github.com/RajeshPhulwaria006/vanishing-gradient-study.git
cd vanishing-gradient-study