# Email Spam Detection Model

## Project Overview

This project builds a machine learning model that classifies emails as **Spam** or **Ham (Not Spam)** using natural language processing.

The project uses a **synthetic dataset created specifically for this submission**. The dataset contains email subjects, email bodies, sender domains, simple metadata features, and the target label.

### Objective

Build an end-to-end spam detection workflow:

1. Load and validate the dataset.
2. Combine email subject and body text.
3. Convert text into numerical TF-IDF features.
4. Train a Logistic Regression classifier.
5. Evaluate the model using accuracy, precision, recall, F1-score, and a confusion matrix.
6. Test the classifier on new email examples.

## Files

| File | Purpose |
|---|---|
| `Milan_Kumar_Email_Spam_Detection.ipynb` | Complete Jupyter Notebook containing the project code |
| `email_spam_synthetic_dataset.csv` | Synthetic dataset used by the model |
| `requirements.txt` | Python libraries required to run the project |
| `Milan_Kumar_Email_Spam_Detection_ProjectReport.docx` | Complete project report |
| `README.md` | Project overview and setup instructions |

## Dataset

The dataset is synthetic and contains **3,500 email records**.

- Ham emails: **2,100**
- Spam emails: **1,400**
- Features include:
  - `email_id`
  - `subject`
  - `body`
  - `sender_domain`
  - `has_link`
  - `num_exclamation`
  - `label`
  - `text`

### Label definition

- `0` = Ham / Not Spam
- `1` = Spam

The data is intentionally synthetic, so it should be used for demonstrating the machine learning workflow rather than claiming real-world spam detection performance.

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- TF-IDF
- Logistic Regression
- Matplotlib
- Seaborn
- Jupyter Notebook

## Model Architecture

**Email Subject + Body → TF-IDF Vectorization → Logistic Regression → Spam/Ham Prediction**

### Why TF-IDF?

TF-IDF gives higher importance to words and word combinations that are informative for a document while reducing the influence of extremely common terms.

### Why Logistic Regression?

Logistic Regression is a strong, interpretable baseline for binary text classification and is computationally efficient for TF-IDF features.

## Setup and Run

### 1. Install Python

Use Python 3.10 or newer.

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the notebook

Open:

`Milan_Kumar_Email_Spam_Detection.ipynb`

Make sure `email_spam_synthetic_dataset.csv` is in the same folder as the notebook.

### 5. Run all cells

The notebook performs data validation, training, evaluation, confusion-matrix visualization, and prediction on new emails.

## Evaluation

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

For a spam filter, precision and recall are especially important because both false positives and false negatives have practical consequences.

## Current Synthetic-Dataset Result

Using an 80/20 stratified train-test split with `random_state=42`:

- Accuracy: **1.0000**
- Precision: **1.0000**
- Recall: **1.0000**
- F1 Score: **1.0000**

These values are specific to the synthetic dataset and should not be presented as evidence of production performance.

## Limitations

1. The dataset is synthetic rather than collected from real mailboxes.
2. Synthetic templates can make the classification problem easier than real-world spam detection.
3. Real spam changes over time, so production systems need continuous monitoring and retraining.
4. Real systems should consider multilingual text, obfuscation, phishing URLs, attachments, sender reputation, and adversarial behavior.
5. Privacy and security controls are required when processing real emails.

## Future Improvements

- Add a much larger and more diverse real-world dataset.
- Compare Logistic Regression with Naive Bayes, Linear SVM, and transformer-based models.
- Add character-level TF-IDF to handle obfuscated spam.
- Add sender/domain reputation features.
- Add URL and attachment risk signals.
- Tune the classification threshold based on the operational cost of false positives and false negatives.
- Build a small Streamlit web interface for live email classification.
