# Final Project: Human Activity Recognition Based on PCA and Convolutional Neural Networks

## 1. Project overview

This notebook implements a customized PCA-CNN model to achieve the following objectives:
1.	Analyze the feature structure, class distribution, and data characteristics of the UCI HAR dataset.
2.	Employ SVM, Random Forest, and Logistic Regression as baseline methods.
3.	Compare the performance of the customized PCA-CNN model and the baseline models.
4.	Evaluate the model performance results through accuracy, macro-precision, macro-recall, macro-F1, confusion matrices and classification reports, and exploratory paired Wilcoxon signed-rank tests.

## 2. The UCI HAR dataset

The dataset used by the notbook exists in the dictionary './data/'. 
```text
data/
├── features.txt
├── X_train.txt
├── y_train.txt
├── subject_train.txt
├── X_test.txt
├── y_test.txt
└── subject_test.txt
```

## 3. Activity classes

The target labels are converted from the the UCI HAR dataset's 1–6 convention to zero-based labels 0–5:
1. Walking
2. Walking Upstairs
3. Walking Downstairs
4. Sitting
5. Standing
6. Laying

## 4. Requirements

- Python 3.10 or 3.11 recommended
- Jupyter Notebook or JupyterLab
- NumPy, pandas, Matplotlib, Seaborn
- PyTorch
- scikit-learn
- SciPy

## 5. How to run

1. Install requirements.
2. Place the dataset files in `./data/`.
3. Open `final_report.ipynb` in Jupyter.
4. Run all cells from top to bottom.
