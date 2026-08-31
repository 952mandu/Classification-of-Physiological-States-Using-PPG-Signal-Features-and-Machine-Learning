# Classification-of-Physiological-States-Using-PPG-Signal-Features-and-Machine-Learning
PPG-Based Physiological State Classification

This project develops a signal processing and machine learning pipeline to classify resting (sitting) vs. active (running) physiological states from photoplethysmography (PPG) signals using the PhysioNet Pulse Transit Time dataset. PPG recordings are bandpass filtered, segmented into overlapping windows, and processed using pulse-peak detection to extract heart rate and pulse amplitude features. A Random Forest classifier is then used for binary classification.

After segmentation, the dataset contained 3,719 samples, and the final model achieved 86.4% accuracy, an F1-score of approximately 0.86, and a ROC-AUC of 0.935. Feature importance analysis was also performed to investigate which PPG-derived physiological features contributed most to classification performance.# Classification of Physiological States Using PPG Signal Features and Machine Learning

A biomedical signal-processing and machine-learning project for classifying resting vs. active physiological states using photoplethysmography (PPG) signals.

## Overview

This project investigates whether features extracted from PPG signals can distinguish between resting and active physiological states.

The project initially explored blood-pressure estimation from PPG. Due to limitations in the available continuous blood-pressure data, the objective was refined to classify **sitting (rest)** versus **running (active)** conditions.

## Dataset

Data were obtained from the **PhysioNet Pulse Transit Time PPG Database**.

The dataset contains physiological recordings collected from approximately 22 subjects under:

- Sitting
- Walking
- Running

For this project, only **sitting and running recordings** were used for binary classification.

The `pleth_1` PPG channel was used for signal analysis.

## Signal Processing Pipeline

The PPG signals were processed using:

1. **Bandpass filtering (0.5–5 Hz)** to reduce baseline drift and high-frequency noise.
2. **Peak detection** to identify individual pulse cycles.
3. **Window segmentation** to divide continuous recordings into shorter samples.
4. **Feature extraction** from each segment.

## Extracted Features

Four PPG-derived features were used:

- Mean heart rate
- Heart rate variability
- Mean pulse amplitude
- Pulse amplitude variability

After segmentation, the dataset contained **3,719 samples**.

## Machine Learning

A **Random Forest Classifier** was trained to distinguish:

- `0` — Sitting / Rest
- `1` — Running / Active

An 80/20 train-test split was used for model evaluation.

## Results

The final model achieved:

| Metric | Performance |
|---|---:|
| Accuracy | 86.4% |
| F1 Score | ~0.86 |
| ROC-AUC | 0.935 |
| Test Samples | 744 |

Feature-importance analysis indicated that **mean heart rate and pulse-amplitude variability** were among the strongest predictors of physiological state.

## Tools

- Python
- NumPy
- SciPy
- WFDB
- scikit-learn
- Matplotlib
- PhysioNet

## Project Workflow

PPG Signal → Filtering → Peak Detection → Segmentation → Feature Extraction → Random Forest → Classification

## Limitations

The original dataset contains a relatively small number of subjects. Segmentation increases the number of machine-learning samples, but segments originating from the same recording are not completely independent.

Future improvements could include subject-level cross-validation, additional PPG features, larger datasets, and comparison with other machine-learning approaches.

## Author

**Manjula Adiveppa Wader**

Biomedical Data Analytics  
University of Southern California
