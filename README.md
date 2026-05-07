# IMDB Reviews Sentiment Analysis

## Project Overview

This project develops a machine learning model to automatically classify IMDB movie reviews as positive or negative. The goal is to achieve an F1 score of at least 0.85 for the Film Junky Union, a community for classic movie enthusiasts, to filter and categorize reviews.

## Dataset

The dataset consists of IMDB movie reviews with polarity labels (positive/negative). It includes features like review text, ratings, votes, and timestamps. The data is split into training and test sets.

## Methodology

### Data Preprocessing
- Loaded data from `imdb_reviews.tsv`
- Handled missing values by dropping incomplete rows
- Normalized text by converting to lowercase and removing non-alphabetic characters
- Performed exploratory data analysis (EDA) to understand data distribution

### Feature Engineering
- Used TF-IDF vectorization for text features
- Applied different preprocessing techniques:
  - NLTK for tokenization and stopword removal
  - spaCy for lemmatization

### Models Evaluated
1. **Model 0 (Baseline)**: Constant prediction
2. **Model 1**: NLTK preprocessing + TF-IDF + Logistic Regression
3. **Model 2**: NLTK preprocessing + TF-IDF + Logistic Regression (optimized)
4. **Model 3**: spaCy preprocessing + TF-IDF + Logistic Regression
5. **Model 4**: spaCy preprocessing + TF-IDF + LightGBM

### Evaluation Metrics
- F1 Score (primary metric, target ≥ 0.85)
- Accuracy
- ROC-AUC
- Average Precision Score

## Results

| Model | Train F1 | Test F1 | Meets Requirement |
|-------|----------|---------|-------------------|
| Model 0 | 0.000 | 0.000 | No |
| Model 1 | 0.879 | 0.858 | Yes |
| Model 2 | 0.894 | 0.883 | Yes |
| Model 3 | 0.890 | 0.878 | Yes |
| Model 4 | 0.868 | 0.858 | Yes |

**Best Model**: Model 2 (NLTK + TF-IDF + Logistic Regression) with Test F1 = 0.883

## Requirements

- Python 3.x
- Libraries: pandas, numpy, scikit-learn, nltk, spacy, matplotlib, seaborn, tqdm
- spaCy model: `en_core_web_sm`

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/arodowicz/IMDB-reviews.git
   cd IMDB-reviews
   ```

2. Install required packages:
   ```bash
   pip install pandas numpy scikit-learn nltk spacy matplotlib seaborn tqdm
   ```

3. Download spaCy model:
   ```bash
   python -m spacy download en_core_web_sm
   ```

## Usage

1. Open the Jupyter notebook:
   ```bash
   jupyter notebook IMDB_Reviews.ipynb
   ```

2. Run all cells in order to:
   - Load and preprocess data
   - Perform EDA
   - Train and evaluate models
   - Compare results

## Key Findings

- The dataset is well-balanced, reducing the need for resampling
- TF-IDF with Logistic Regression performs best for this task
- Both NLTK and spaCy preprocessing yield strong results
- All top models generalize well with minimal overfitting

## Conclusion

This project successfully delivers a sentiment classification model exceeding the F1 requirement of 0.85. Model 2 is recommended for deployment due to its superior performance and robustness across multiple metrics.</content>
<parameter name="filePath">c:\Users\ARodowicz\Desktop\projects\IMDB_Reviews\README.md