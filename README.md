Hand Gesture Classification Using MediaPipe Landmarks from the HaGRID Dataset
Overview
This project focuses on classifying hand gestures using landmark data extracted by MediaPipe from the HaGRID (Hand Gesture Recognition Image Dataset). The goal is to train a machine learning model capable of accurately classifying gestures based on the x, y, z coordinates of hand landmarks.

Students will gain experience in:
✅ Data preprocessing and visualization
✅ Model training and evaluation
✅ Documentation and presentation of results

Dataset Details
The HaGRID dataset contains 18 hand gesture classes.
Each gesture is represented by 21 hand landmarks (x, y, z) extracted using MediaPipe.
The dataset is provided as a CSV file, where each row contains:
Landmark coordinates (x, y, z) for 21 keypoints
Gesture label
Preprocessing Notes:
Hand landmarks vary in scale and position. To standardize them:
Recenter (x, y) coordinates to make the wrist point the origin.
Normalize landmarks by dividing by the mid-finger tip position.
The z-location does not require further processing.
Stabilize output predictions by applying a moving mode filter over a window.
Project Deliverables
✅ 1. Google Colab Notebook
A well-documented notebook uploaded to GitHub that includes:
📌 Data Loading: Importing the CSV file and understanding its structure.
📌 Data Visualization: Plotting sample hand landmarks.
📌 Preprocessing: Cleaning and normalizing the data, handling missing values, and splitting into train/test sets.
📌 Model Training: Implementing and comparing at least three ML models (e.g., Random Forest, SVM).
📌 Evaluation: Reporting accuracy, precision, recall, and F1-score.
📌 Conclusion: Summarizing results and selecting the best model.

✅ 2. Output Video
🎥 A short video demonstrating the trained model in action:

MediaPipe extracts hand landmarks from each frame.
Predictions are displayed in real-time.
The video must be uploaded to Google Drive with a public link.
Evaluation Criteria
✅ Code Quality – Clean, well-documented, and reproducible.
✅ Model Performance – Accuracy and robustness of trained models.
✅ Visualization – Clear representation of data and results.

