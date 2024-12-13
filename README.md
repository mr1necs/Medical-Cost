# Medical-Insurance

## Overview
This project demonstrates the implementation of linear regression models (both base and polynomial) for predicting insurance charges based on customer information. The models are trained using both analytical methods and gradient descent, without relying on pre-built machine learning libraries for the core algorithms.

## Dataset
The dataset used in this project is `insurance.csv`, which contains the following features:

| Column     | Description                      |
|------------|----------------------------------|
| `age`      | Age of the individual            |
| `sex`      | Gender (`male` or `female`)      |
| `bmi`      | Body Mass Index                  |
| `children` | Number of children/dependents    |
| `smoker`   | Smoking status (`yes` or `no`)   |
| `region`   | Region of residence              |
| `charges`  | Insurance charges (target)       |

### Data Preprocessing
1. **Handling Missing Data:** The dataset is complete without missing values.
2. **Feature Encoding:**
   - `sex` is encoded as `male: 0`, `female: 1`.
   - `smoker` is encoded as `yes: 1`, `no: 0`.
   - `region` is encoded as `southwest: 0`, `southeast: 1`, `northwest: 2`, `northeast: 3`.
3. **Normalization:** Numeric features are normalized for uniform scaling.
4. **Dimensionality Reduction:** Principal Component Analysis (PCA) is applied to retain features contributing at least 98% of the variance.
5. **Polynomial Feature Expansion:** Features are expanded up to degree 3 using polynomial transformations.

## Models
Two types of models were implemented:

1. **Base Linear Model:**
   - Uses features after PCA.
   - Trained using both analytical solution and gradient descent.

2. **Polynomial Model:**
   - Uses polynomial features derived from the base features.
   - Trained using both analytical solution and gradient descent.

### Training
- The dataset is split into training (70%) and testing (30%) sets.
- Both models are trained using:
  1. **Analytical Solution:** Closed-form solution using the normal equation.
  2. **Gradient Descent:** Iterative optimization with learning rate 0.0001 and 100,000 iterations.

## Evaluation
Models are evaluated using the following metrics:
- **Mean Absolute Error (MAE):** Average absolute differences between predicted and actual values.
- **Mean Squared Error (MSE):** Average squared differences between predicted and actual values.
- **R² Score:** Proportion of variance explained by the model.

### Results
| Model                      | MAE       | MSE         | R²   |
|----------------------------|-----------|-------------|-------|
| Base (Linear, Analytical)  | 4626.667  | 46572520.118 | 0.716 |
| Polynomial (Linear, Analytical) | 24200.550 | 1112706882.143 | -6.813 |
| Base (Gradient)            | 4994.318  | 50798276.181 | 0.691 |
| Polynomial (Gradient)      | 3542.239  | 32325540.171 | 0.773 |

## Key Findings
- The base model performs reasonably well with both analytical and gradient descent methods.
- The polynomial model demonstrates overfitting when trained analytically but improves with gradient descent.

## How to Run
1. Ensure the following Python libraries are installed:
   ```bash
   pip install numpy pandas scikit-learn
   ```
2. Place the `insurance.csv` file in the working directory.
3. Run the script to see the outputs, including coefficients and evaluation metrics.

## Future Improvements
- Hyperparameter tuning for gradient descent.
- Additional regularization to mitigate overfitting in the polynomial model.
- Exploration of alternative feature engineering techniques.

## Author
Developed by [Mr1necs]. Feel free to reach out for questions or collaborations!

