# Edge-IoMT Adversarial Defense Framework

An adaptive, hardware-efficient security framework designed to protect continuous, in-transit IoMT (Internet of Medical Things) ECG telemetry against Adversarial Machine Learning exploits.

## 📌 Project Overview
Wearable medical IoT devices (like smartwatches and cardiac monitors) continuously stream cardiovascular data to the cloud for automated AI diagnosis. However, these systems are highly vulnerable to adversarial injection attacks such as the **Fast Gradient Sign Method (FGSM)**. An attacker can intercept and introduce imperceptible mathematical perturbations into the raw ECG stream, causing deep learning classifiers (like 1D-CNNs) to trigger fatal medical misdiagnoses.

Since Edge-IoMT devices operate under extreme memory and battery constraints, traditional heavy defenses (like adversarial retraining) are practically unfeasible. This project introduces a **Lightweight Moving Average Denoising Layer** that sanitizes incoming corrupted signals at sub-kilobyte memory footprints before they reach the AI model.

## ⚙️ System Architecture
1. **Data Ingestion:** Loads gold-standard clinical ECG inputs from the MIT-BIH Arrhythmia Database.
2. **Base Classifier:** Evaluates real-time health telemetry using a custom 1D-Convolutional Neural Network (1D-CNN) built in PyTorch.
3. **Threat Simulation:** Injects an adversarial FGSM cyber-attack ($\epsilon = 0.15$) to deliberately blind the AI model.
4. **Edge Defense:** Routes the corrupted stream through an ultra-fast, hardware-efficient mathematical moving average smoothing matrix to restore diagnostic integrity in real-time.

## 📊 Empirical Evaluation Summary
* **Baseline Accuracy (Clean Telemetry):** Peak performance on uncorrupted cardiovascular data.
* **Adversarial Accuracy (Under FGSM Attack):** Experiences a critical accuracy drop, proving structural vulnerability.
* **Defended Accuracy (With Proposed Filter):** Successfully recovers diagnostic reliability without heavy processing overhead.

## 🚀 Future Development
* Validating the framework against diverse black-box optimization attacks.
* Porting and compiling the lightweight code directly onto physical ARM Cortex-M microcontrollers to measure live battery and processing cycle consumption.

---
**Author:** Hasitha Lakshan  
**Institution:** Sri Lanka Technology Campus (SLTC)
