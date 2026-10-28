# Greenpod_Avocado_Ripening_Project
# Avocado Ripening Stage Detection and Classification

## Greenpod Labs — Data Science Assignment 2

## 1. Project Overview

Avocado Ripening Stage Detection and Classification is a computer vision and deep learning project designed to classify avocados according to their ripening stages using images.

The project implements and compares two approaches:

1. **Classical Computer Vision:** OpenCV feature extraction using HSV color histograms and HOG texture features, followed by an SVM classifier.
2. **Deep Learning:** MobileNetV2 transfer learning for image classification.

The objective is to evaluate both approaches and identify the most effective model using appropriate evaluation metrics.

## 2. Objectives

- Analyze the avocado image dataset.
- Identify class imbalance, duplicate images, unreadable files, and potential dataset biases.
- Build a classical computer vision classification model.
- Build a deep learning classification model.
- Compare model performance using multiple evaluation metrics.
- Test predictions on sample avocado images.
- Discuss production performance, limitations, and future improvements.

## 3. Technologies Used

- Python
- OpenCV
- NumPy
- Pandas
- Scikit-learn
- TensorFlow and Keras
- MobileNetV2
- Matplotlib and Seaborn
- Pillow

## 4. Project Folder Structure

```text
Greenpod_Avocado_Ripening_Project/
├── data/
│   ├── raw/
│   └── split/
├── models/
├── reports/
├── src/
│   ├── __init__.py
│   ├── audit_dataset.py
│   ├── split_dataset.py
│   ├── features.py
│   ├── train_classical.py
│   ├── train_cnn.py
│   ├── compare_models.py
│   └── predict.py
├── requirements.txt
├── report_template.md
└── README.md
```

## 5. Dataset

Download the dataset from the Google Drive link provided in the assignment:

[Download the Avocado Dataset](https://drive.google.com/file/d/1NMJ0FOxcWH1mwFFeERuY6fgEY-MVgeET/view)

Extract the dataset into the `data/raw/` directory.

Organize the images into folders according to the actual ripening-stage labels provided by the dataset.

Example:

```text
data/raw/
├── unripe/
├── ripe/
└── overripe/
```

The actual class names and image counts must be confirmed by inspecting the downloaded dataset.

## 6. Installation and Setup

### Prerequisites

- Python 3.10 or 3.11
- Visual Studio Code
- Git (optional, for version control)
- An internet connection for installing packages and downloading pretrained weights

### Windows Setup

Open PowerShell in the project directory.

Create a virtual environment:

```powershell
py -m venv .venv
```

Activate the environment:

```powershell
.\.venv\Scripts\Activate.ps1
```

Upgrade pip:

```powershell
python -m pip install --upgrade pip
```

Install the required dependencies:

```powershell
pip install -r requirements.txt
```

## 7. Dataset Inspection

Run the dataset audit script:

```powershell
python src\audit_dataset.py --data data\raw
```

The script examines image counts, image dimensions, duplicate files, and unreadable images.

Reports are saved in the `reports/` directory.

## 8. Dataset Splitting

Split the dataset into training, validation, and testing sets:

```powershell
python src\split_dataset.py --input data\raw --output data\split
```

The approximate split is:

- Training: 70%
- Validation: 15%
- Testing: 15%

The test set is reserved for evaluating the trained models.

## 9. Approach 1: Classical Computer Vision

This approach extracts
