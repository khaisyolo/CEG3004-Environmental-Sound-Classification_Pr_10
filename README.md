# CEG3004 Environmental Sound Classification (Pr_10)

DSP Mini Project for **CEG3004 Digital Signal Processing**.

This project implements a **Digital Signal Processing (DSP) pipeline and machine learning model** to classify environmental sounds into **50 categories**.

---

# Project Objective

The goal of this project is to design a **robust environmental sound classification system** that performs well under different audio distortions.

The system is evaluated on:

* Clean audio signals
* Noisy audio signals
* Band-limited audio signals

The model extracts DSP features from audio clips and predicts the corresponding sound class.

---

# Dataset

The dataset is derived from the **ESC-50 environmental sound dataset**.

Dataset characteristics:

* 50 sound classes
* 5-second audio clips
* Mono waveform
* Sample rate: 16 kHz

The dataset is divided into two parts.

## Training Set

* 1200 labelled audio clips

## Submission Set

Each audio clip appears in three forms:

* Clean audio
* Noisy audio
* Band-limited audio

These variations test the **robustness of the DSP pipeline and classifier**.

---

# System Pipeline

The environmental sound classification system follows this pipeline:

Audio Input
↓
Audio Preprocessing
↓
Feature Extraction (MFCC + Spectral Features)
↓
Feature Statistics (Mean & Standard Deviation)
↓
Machine Learning Classifier
↓
Predicted Sound Class

---

# DSP Pipeline

## 1. Audio Preprocessing

The preprocessing stage improves signal consistency before feature extraction.

Preprocessing steps include:

* Silence trimming
* Peak normalization
* Pre-emphasis filtering
* Fixed-length padding/truncation (5 seconds)

These steps ensure all audio clips have consistent signal properties.

---

## 2. Feature Extraction

Several **Digital Signal Processing (DSP) features** are extracted from each audio clip.

### MFCC Features

Mel Frequency Cepstral Coefficients (MFCCs) represent spectral information of the signal based on the human auditory system.

### Delta Features

Temporal information is captured using:

* Delta MFCC (first derivative)
* Delta-Delta MFCC (second derivative)

### Spectral Features

Additional spectral descriptors include:

* Spectral centroid
* Spectral bandwidth
* Spectral rolloff
* Zero-crossing rate
* RMS energy

### Feature Statistics

To obtain a fixed-length feature vector, statistical pooling is applied:

* Mean
* Standard deviation

---

# Machine Learning Model

The classification model is implemented using a **Scikit-learn pipeline**.

Pipeline components:

* StandardScaler
* Support Vector Machine (SVM)

The model is trained on the labelled dataset and evaluated using validation data.

---

# Model Performance

Validation results:

Accuracy: **0.56**
Macro F1 Score: **0.54**

These results indicate that the DSP feature pipeline successfully captures meaningful acoustic patterns for environmental sound classification.

---

# Visualization

The notebook includes visualizations to analyse the audio signals:

* Time-domain waveform plots
* Frequency-domain spectrograms
* Interactive audio playback

These visualizations help understand the acoustic characteristics of environmental sounds.

---

# Error Analysis

Some classes such as airplane, wind, and helicopter achieved lower recall.

This is likely because these classes share similar low-frequency spectral characteristics, making them harder to separate using MFCC-based classical features.

Future work may use CNN-based spectrogram learning to improve separation of acoustically similar classes.

# Repository Structure

```
CEG3004-Environmental-Sound-Classification_Pr_10
│
├── README.md
├── CEG3004_Project_Colab_Pr_10.ipynb
└── requirements.txt
```

---

# How to Run

## Install dependencies

pip install -r requirements.txt

## Run the notebook

Open and execute:

CEG3004_Project_Colab_Pr_10.ipynb

The notebook will:

* extract DSP features
* train the machine learning model
* generate predictions
* save the trained model

Output files generated:

Pr_10_model.joblib
Pr_10_predictions.csv

---

# Limitations and Future Work

Although the model achieves reasonable performance, several improvements could be explored:

* Deep learning models (CNNs) using spectrogram inputs
* Data augmentation for improved noise robustness
* Additional spectral features such as chroma or mel-spectrogram features
* Hyperparameter tuning for better classifier performance

---

# Author

Group ID: **Pr_10**
Course: **CEG3004 Digital Signal Processing**
