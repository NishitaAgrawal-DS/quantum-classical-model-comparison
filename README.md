Quantum–Classical Model Comparison

Benchmarking classical neural networks, hybrid quantum–classical models, and fully quantum variational classifiers on a real-world binary classification task using PyTorch and PennyLane.

📌 Overview

This project presents a systematic comparison between:

A classical Multilayer Perceptron (MLP)

A hybrid quantum–classical neural network

A fully quantum Variational Quantum Classifier (VQC)

All models are evaluated under a consistent preprocessing pipeline, identical datasets, and standard performance metrics. The goal is to analyze the practical benefits, limitations, and trade-offs of quantum machine learning models compared to strong classical baselines.

🎯 Objectives

Implement and train three distinct learning paradigms:

Classical

Hybrid quantum–classical

Fully quantum

Perform a fair, controlled comparison using the same dataset and evaluation metrics

Study:

Model performance (Accuracy, F1-score, ROC-AUC)

Training stability

Parameter efficiency

Computational feasibility on near-term quantum simulators

Provide a reproducible benchmarking framework for quantum ML research and learning

🧠 Models Implemented
1. Classical Neural Network (Baseline)

Architecture: Multilayer Perceptron (MLP)

Input features: 30

Hidden layers:

64 neurons (ReLU)

32 neurons (ReLU)

Output: 2-class logits

Framework: PyTorch

2. Hybrid Quantum–Classical Model

Classical part:

Linear layer: 30 → 4

tanh activation to map features to 
[
−
1
,
1
]
[−1,1]

Quantum part:

4-qubit variational quantum circuit

2 quantum layers

Trainable RY rotations + CNOT entanglement

Output:

4 expectation values → classical linear layer → logits

Frameworks: PyTorch + PennyLane

3. Fully Quantum Model (VQC)

Quantum-only classifier

Qubits: 4

Feature encoding: RY rotations

Trainable parameters: 1 per qubit

Entanglement: Linear CNOT chain

Measurement: Pauli-Z expectation

Loss: Mean Squared Error on expectation values

Framework: PennyLane

🧪 Dataset & Preprocessing

Dataset: Breast Cancer Wisconsin (Diagnostic)

Samples: 569

Features: 30

Classes: 2 (binary classification)

Preprocessing:

Standardization (zero mean, unit variance)

Stratified train–test split (80% / 20%)

Quantum models:

Use first 4 features (equal to number of qubits)

⚙️ Methodology

Data preprocessing

Scaling and stratified splitting

Model training

Independent training loops for each model

End-to-end gradient-based optimization

Evaluation

Accuracy

F1-score

ROC-AUC

Confusion Matrix

Controlled setup

Fixed random seeds

Identical train–test splits

Same evaluation metrics

📊 Results (Summary)

Exact numerical results depend on random initialization and simulator settings.

General observations:

Classical MLP

Strong baseline performance

Fast and stable convergence

Hybrid Model

Competitive performance with fewer parameters

Demonstrates effective quantum–classical interaction

Fully Quantum VQC

Works on low-dimensional data

Limited by qubit count and circuit expressivity

Higher training variance

The results highlight that hybrid models currently offer the best trade-off between performance and quantum feasibility on near-term devices.
