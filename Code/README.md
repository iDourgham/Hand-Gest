# Hand Gesture Classification Using MediaPipe Landmarks from HaGRID Dataset

## Overview
This project aims to classify hand gestures using the **HaGRID dataset** and **MediaPipe Hand Landmarks**. The main objective is to extract meaningful features from hand images, preprocess the data, and train various machine learning models to achieve high classification accuracy.

## Dataset: HaGRID
The **HaGRID (Hand Gesture Recognition Image Dataset)** contains labeled images of different hand gestures. We utilize **MediaPipe** to extract 2D hand landmarks, which serve as feature inputs for our machine learning models.

## Methodology
1. **Data Preprocessing**
   - Load and clean the dataset.
   - Extract **hand landmarks** using **MediaPipe**.
   - Encode class labels using **Label Encoding**.
   - Split the data into training and testing sets.
   - Normalize features using **StandardScaler**.

2. **Model Training and Evaluation**
   - **Random Forest Classifier**: Initial model to benchmark performance.
   - **Hyperparameter Tuning**: Using `RandomizedSearchCV` to optimize hyperparameters.
   - **XGBoost Classifier**: Explored for improved performance.
   - **SVM Classifier**: Evaluated with different kernels and hyperparameters.
   - **Performance Metrics**: Accuracy, Precision, Recall, F1-score.

## Project Structure
```
├── dataset/                     # Contains raw and processed data
│   ├── hand_landmarks_data.csv   # Processed dataset with extracted features
│   ├── HaGRID_images/            # Original images from HaGRID (if used)
│
├── models/                      # Saved trained models
│   ├── best_random_forest.pkl    # Optimized Random Forest model
│   ├── best_xgboost.pkl          # Optimized XGBoost model
│   ├── best_svm.pkl              # Optimized SVM model
│
├── src/                         # Source code for model training and evaluation
│   ├── preprocess.py             # Data preprocessing steps
│   ├── train_models.py           # Training different classifiers
│   ├── evaluate.py               # Model performance evaluation
│
├── notebooks/                   # Jupyter notebooks for experimentation
│
├── README.md                    # Project documentation
├── requirements.txt              # Dependencies required to run the project
```

## Results
| Model                | Train Accuracy | Test Accuracy |
|----------------------|---------------|--------------|
| Random Forest       | 99.74%        | 97.68%       |
| XGBoost            | 100%        | 98.8%       |
| SVM                | 99.40%        | 98.79%       |

**Key Findings:**
- The best-performing model achieved **98.8% accuracy**.
- Hyperparameter tuning significantly improved model generalization.
- Feature selection played a critical role in model performance.


## Contributors
- **Mohamed Mohy** ([GitHub Profile](https://github.com/iDourgham))
                   ([LinkedIn Profile](https://www.linkedin.com/in/eng-m-mohy/))

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

