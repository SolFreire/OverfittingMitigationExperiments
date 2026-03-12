# Overfitting and Regularization Experiments in Neural Networks

## Overview

This repository presents a set of controlled experiments designed to demonstrate the effects of overfitting in neural networks and to analyze how different optimization and regularization techniques influence model generalization.

The baseline experiment intentionally induces overfitting by training the model for a large number of epochs without any regularization mechanism. This setup allows the divergence between training and validation performance to be clearly observed.

After establishing the baseline behavior, several commonly used techniques in deep learning optimization are applied to evaluate their impact on model performance.

---

## Techniques Evaluated

The following methods were tested to analyze their effect on training dynamics and generalization:

* Gradient Descent with Momentum
* Adam Optimizer
* L2 Regularization

Each technique was applied independently to observe how it affects the gap between training, validation, and test errors.

---

## Experimental Setup

The same dataset and neural network architecture were used across all experiments.

Overfitting was intentionally induced by increasing the number of training epochs without applying regularization.

Model performance was evaluated using three metrics:

* **Training Error**
* **Validation Error**
* **Test Error**

These metrics allow us to analyze both the learning behavior of the model and its ability to generalize to unseen data.

---

## Results

| Method                         | Training Error | Validation Error | Test Error |
| ------------------------------ | -------------- | ---------------- | ---------- |
| Baseline (Overfitting induced) | 0.0371         | 0.2678           | 0.2738     |
| Momentum                       | 0.0173         | 0.2549           | 0.2460     |
| Adam Optimizer                 | 0.0000         | 0.2945           | 0.2663     |
| L2 Regularization (λ = 0.005)  | 0.0477         | 0.1867           | 0.1455     |

---

## Discussion

The baseline configuration clearly shows the presence of overfitting, as indicated by the large gap between training and validation errors.

The addition of momentum slightly improves performance but does not significantly reduce the generalization gap.

The Adam optimizer leads to extremely low training error, suggesting that the model fits the training data very closely. However, validation and test errors remain relatively high, indicating that overfitting now is worst.

L2 regularization produces the best overall results among the tested techniques. Although the training error increases slightly, both validation and test errors decrease substantially, indicating improved generalization.

---

## Purpose

The purpose of this repository is educational. It provides a clear and reproducible demonstration of how optimization algorithms and regularization techniques influence neural network training, particularly in the presence of overfitting.
