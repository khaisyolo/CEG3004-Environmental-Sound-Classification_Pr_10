# CEG3004 Environmental Sound Classification (Pr_10)

DSP Mini Project for **CEG3004 Digital Signal Processing**.

This project implements a **Digital Signal Processing (DSP) pipeline and machine learning model** to classify environmental sounds into 50 categories.

---

# Project Objective
The aim of this project is to design a **robust environmental sound classification system** that performs well under:

- Clean audio signals
- Noisy audio signals
- Band-limited audio signals

The system extracts DSP features from audio clips and uses a machine learning classifier to predict the sound class.

---

# Dataset
The dataset is derived from the **ESC-50 environmental sound dataset**.

Dataset characteristics:

- 50 sound classes
- 5-second audio clips
- Mono waveform
- Sample rate: 16 kHz

The dataset is divided into:

Training set  
- 1200 labelled audio clips

Submission set  
- Clean audio
- Noisy audio
- Band-limited audio

---

# DSP Pipeline

## 1. Audio Preprocessing
The audio preprocessing stage includes:

- Silence trimming
- Peak normalization
- Pre-emphasis filtering
- Fixed-length padding/truncation (5 seconds)

These steps improve signal consistency before feature extraction.

---

## 2. Feature Extraction
Several DSP-based audio features are extracted:

- MFCC (Mel Frequency Cepstral Coefficients)
- Delta MFCC
- Delta-delta MFCC
- Spectral centroid
- Spectral bandwidth
- Spectral rolloff
- Zero-crossing rate
- RMS energy

Statistical pooling (mean and standard deviation) is applied to convert frame-level features into a fixed-length feature vector.

---

## 3. Machine Learning Model
The classification model uses:

Pipeline:
- StandardScaler
- Support Vector Machine (SVM)

The model is trained on the labelled dataset and evaluated using validation data.

---

# Model Performance

Validation Results:

Macro F1 Score ≈ **0.54**

This performance demonstrates that the DSP feature pipeline is able to capture meaningful acoustic patterns for environmental sound classification.

---

# How to Run

1. Install dependencies
2. Run the notebook
3. The model and predictions will be generated automatically.

Output files:
Pr_10_model.joblib
Pr_10_predictions.csv

# Author

Group ID: **Pr_10**  
Course: **CEG3004 Digital Signal Processing**
