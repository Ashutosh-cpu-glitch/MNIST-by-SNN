# Spiking Neural Network for MNIST Classification

This project implements a Spiking Neural Network (SNN) for handwritten digit classification using the MNIST dataset. The goal is to explore how spike-based neural models can perform standard vision tasks using temporal processing.

---

## Overview

Unlike traditional neural networks, SNNs operate using discrete spike events over time. In this implementation:

* Static images are converted into spike trains using rate-based encoding
* The network processes inputs over multiple timesteps using LIF neurons
* Output spikes are accumulated over time to perform classification

This setup allows the model to learn from temporal spike activity rather than continuous activations.

---

## Method

### 🔹 Spike Encoding (Rate Coding)

Input images are transformed into spike trains:

* Pixel intensity is interpreted as spike probability
* Higher intensity → higher firing rate
* Spike sequences are generated over fixed timesteps

### 🔹 Model Architecture

The network consists of:

* Fully connected layer → LIF neuron
* Fully connected layer → LIF neuron

At each timestep:

* Inputs are processed through linear layers
* Membrane states are updated using LIF dynamics
* Output spikes are generated and accumulated

### 🔹 Training Strategy

* Loss function: Cross-Entropy
* Optimizer: Adam
* Learning is performed using surrogate gradients

The final prediction is based on accumulated spike activity over time.

---

## Results

* **Test Accuracy:** ~96.9%
* The model achieves strong performance for a simple spiking architecture
* Temporal integration effectively captures input information

---

## Limitations

* Rate coding introduces stochasticity and may limit efficiency
* The architecture is shallow and not optimized for large-scale tasks
* No direct evaluation on neuromorphic hardware is performed

---

## Key Takeaways

* SNNs can perform classification tasks using spike-based representations
* Temporal spike integration provides a viable mechanism for decision making
* Suggests that the approach could be applied to neuromorphic hardware

---

## Requirements

* Python 3.8+
* PyTorch
* Norse
* torchvision
* NumPy
* Matplotlib

Install dependencies:

```
pip install -r requirements.txt
```

---

## How to Run

1. Clone the repository

2. Open the notebook:

   `snn_mnist_classification.ipynb`

3. Run all cells sequentially

The model will train on MNIST and report classification accuracy.

---

## Notebook

* `snn_mnist_classification.ipynb`

---
