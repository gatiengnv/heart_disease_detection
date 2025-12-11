# Heart Failure Prediction 💔

![img.png](img.png)

## Overview
This project implements a binary classification neural network using Keras/TensorFlow with automated hyperparameter tuning to find optimal model configurations.

## Features
- Binary classification using feedforward neural networks
- Automated hyperparameter search across multiple dimensions
- Model performance tracking and best model selection
- Scalable architecture for testing various configurations

## Installation
```bash
  pip install -r requirements.txt
```

## Model Architecture
- **Input Layer**: Adapts to feature dimensionality
- **Hidden Layers**: Variable number with ReLU activation
- **Output Layer**: Single neuron with sigmoid activation for binary classification

## Hyperparameters Tested
- Number of hidden layers (0-9)
- Hidden layer units (50, 100, 200)
- Learning rates (0.001, 0.01, 0.1)
- Batch sizes (8, 16, 32, 64)
- Training epochs (25, 50, 100)
- Dropout rates (0.0, 0.2, 0.5)

## Usage
```python
# Prepare scaled training and test data
X_train_scaled, X_test_scaled, y_train, y_test

# Run hyperparameter search
# The script will automatically find the best configuration

# Best model parameters are saved and displayed
```

## Model Evaluation
- **Loss Function**: Binary crossentropy
- **Optimizer**: Adam
- **Metrics**: Accuracy
- **Threshold**: 0.5 for binary predictions

## Cross-Validation
The project includes cross-validation for model comparison using KFold with 5 splits. All models are evaluated using the same methodology to ensure fair comparison.

## Results
The script outputs:
- Accuracy for each configuration tested
- Best performing hyperparameter combination
- Final test accuracy of optimal model
- Visualization of model comparisons using boxplots

## Notes
- Data should be scaled before training (using StandardScaler or similar)
- Predictions are converted from probabilities to binary using 0.5 threshold
- Model selection based on test set accuracy
- The 0.5 threshold conversion `(y_test_proba >= 0.5).astype(int)` is essential for proper binary classification

## Performance
The hyperparameter search tests multiple configurations to achieve optimal accuracy. Typical improvements range from 0.40 to 0.80+ accuracy depending on data quality and parameter selection.