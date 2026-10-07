# SHL Grammar Scoring Engine — Version 1

Machine learning solution developed for the **SHL Hiring Assessment 2026** Kaggle challenge.

## Objective

The task is to predict a continuous **Grammar Score from 0 to 5** for spoken English audio recordings.

The system takes an audio recording as input, extracts acoustic features, and predicts the grammar score using an ensemble regression approach.

## Dataset

The assessment dataset contains:

- 769 training audio recordings
- 216 test audio recordings
- WAV audio format
- Mono audio
- 16 kHz sampling rate
- 16-bit PCM audio

The private assessment dataset is not included in this repository.

## Version 1 Approach

Version 1 uses an **acoustic-feature-based machine learning pipeline**.

### Audio Feature Extraction

For each audio recording, the following types of features were extracted:

- RMS energy statistics
- Zero-crossing rate
- Spectral centroid
- Spectral bandwidth
- Spectral rolloff
- Spectral flatness
- MFCC statistics
- Temporal statistics
- Percentile-based acoustic statistics

The final feature representation contains **52 acoustic features per audio recording**.

### Models

Two tree-based regression models were trained:

1. Randomized Tree Ensemble
2. Bagged CART Regression

The final prediction was produced using a weighted ensemble of these models.

## Validation

Five-fold cross-validation was used during model development.

The Version 1 development results were:

| Metric | Result |
|---|---:|
| OOF RMSE | 0.7976 |
| OOF Pearson Correlation | 0.7673 |
| Number of Features | 52 |
| Training Samples | 769 |

## Kaggle Submission

The Version 1 model was submitted successfully to the private SHL Hiring Assessment 2026 Kaggle competition.

**Kaggle Version:** Version 1

**Public Kaggle Score:** `0.7570`

**Submission Status:** Complete

The public score is the official Kaggle result for Version 1.

## Prediction Validation

Before submission, the generated test predictions were checked for:

- Missing predictions
- Duplicate filenames
- Prediction count
- Prediction range

The Version 1 prediction file contained predictions for the available test recordings.

## Project Structure

```text
SHL-Grammar-Scoring-Engine/
│
├── SHL_Grammar_Scoring_Engine.ipynb
├── README.md
├── requirements.txt
└── results/
    └── model_results.json
```

## Notebook

The Jupyter notebook contains the complete Version 1 workflow:

1. Dataset discovery
2. Audio loading
3. Audio feature extraction
4. Feature preparation
5. Model training
6. Cross-validation
7. RMSE evaluation
8. Pearson correlation evaluation
9. Test prediction
10. Prediction validation

## Requirements

The main Python libraries used are:

- NumPy
- Pandas
- Scikit-learn
- Matplotlib

See `requirements.txt` for the package list.

## Reproducibility

The notebook was developed and executed in the Kaggle environment using the competition dataset.

The private SHL assessment audio files are not included in this public GitHub repository.

## Future Improvements

Potential improvements for future versions include:

- Speech-to-text transcription
- Linguistic and grammatical features
- Transformer-based speech representations
- Text-based grammar features
- Audio + text multimodal models
- Model ensembling and calibration

## Author

**Saikiran Deva**

B.Tech — Artificial Intelligence and Machine Learning

Hyderabad, India

## Assessment

**SHL Hiring Assessment 2026**

**Task:** Grammar Scoring Engine
