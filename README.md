# parkinson-disease-
This project is under working
# EEG-based Parkinson's Disease Detection

Pipeline for detecting Parkinson's disease using EEG signals.  
Supports preprocessing, feature extraction, and ML/DL models.

### Steps
1. **Preprocessing**: Bandpass filter, artifact removal, segmentation.
2. **Feature Extraction**: 
   - Spectral power (delta, theta, alpha, beta, gamma)
   - Entropy measures
   - Wavelet transforms
3. **Classification Models**:
   - ML: RandomForest, SVM
   - DL: 1D-CNN for raw EEG segments

### Quickstart
```bash
pip install -r requirements.txt

# Preprocess raw EEG -> numpy arrays
python src/preprocess.py --input data/raw --output data/processed

# Extract features -> CSV
python src/features.py --input data/processed --output data/features.csv

# Train classifier
python src/train.py --data data/features.csv --model randomforest

# Predict
python src/predict.py --model models/saved_model.pth --input data/processed/sample.npy
