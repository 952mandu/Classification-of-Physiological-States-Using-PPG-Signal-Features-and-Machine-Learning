# Classification-of-Physiological-States-Using-PPG-Signal-Features-and-Machine-Learning
PPG-Based Physiological State Classification

This project develops a signal processing and machine learning pipeline to classify resting (sitting) vs. active (running) physiological states from photoplethysmography (PPG) signals using the PhysioNet Pulse Transit Time dataset. PPG recordings are bandpass filtered, segmented into overlapping windows, and processed using pulse-peak detection to extract heart rate and pulse amplitude features. A Random Forest classifier is then used for binary classification.

After segmentation, the dataset contained 3,719 samples, and the final model achieved 86.4% accuracy, an F1-score of approximately 0.86, and a ROC-AUC of 0.935. Feature importance analysis was also performed to investigate which PPG-derived physiological features contributed most to classification performance.
