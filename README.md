# Professor Rating Predictor (NLP + Transformers)

## Overview
This project builds a machine learning model that predicts professor ratings (1–5 stars) based on student reviews.

Using the PlanetTerp API, I collected real review data, built a dataset, and fine-tuned a transformer model to classify ratings from text.

## Goal
Do written student reviews accurately reflect the numerical rating they give?

This project explores that question using NLP and machine learning.

## Data Collection
- Data collected dynamically using the PlanetTerp API
- 5 professors with ≥5 reviews each
- Final dataset: 40 reviews
- Columns: review text, rating, course, etc.

## Model
- Model: DistilBERT (Hugging Face)
- Task: 5-class classification (ratings 1–5)
- Framework: PyTorch + Transformers
- Training:
  - 80/20 train-validation split
  - 3 epochs
  - AdamW optimizer (lr = 2e-5)

## Results
- Validation accuracy: ~37.5%
- Random baseline (5 classes): ~20%
- Model performs better than random and captures general sentiment

## Analysis
- Model correctly identifies positive vs negative tone
- Struggles to predict exact ratings due to:
  - Small dataset size (40 reviews)
  - Class imbalance (more high ratings)
  - Limited training time

## Future Improvements
- Collect more data (more professors + reviews)
- Balance dataset across rating classes
- Experiment with different models / hyperparameters

## Files
- `professor_rating_predictor.ipynb` — full pipeline (data collection → training → evaluation)
- `professor_rating_project_report.pdf` — presentation slides

## How to Run
1. Open the notebook in Google Colab
2. Run all cells
3. Data will be collected automatically from the API
4. Model will train and output predictions
