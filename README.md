# Heart Disease Classification

This project explores how machine learning can be used to predict whether a patient has heart disease based on clinical attributes such as age, blood pressure, cholesterol, chest pain type, maximum heart rate, and other diagnostic indicators.

The work is implemented in the notebook [heart-disease-classification.ipynb](heart-disease-classification.ipynb) and follows a typical end-to-end data science workflow: data loading, exploratory data analysis, feature inspection, model training, hyperparameter tuning, and evaluation.

## Project objective

The central question of the project is:

> Given clinical parameters about a patient, can we predict whether or not they have heart disease?

The notebook sets a proof-of-concept target of achieving 95% accuracy. If that threshold is met, the project can be extended further for broader deployment and real-world use.

## Problem definition

Heart disease remains one of the leading causes of mortality worldwide. Early identification and risk stratification can enable timely intervention and better healthcare decisions. This project aims to build a binary classifier that estimates the likelihood of heart disease from patient data.

The target variable is:

- 0 = No disease
- 1 = Disease

## Dataset

The project includes the dataset file [heart-disease.csv](heart-disease.csv) in the repository root. It is based on the Cleveland Heart Disease dataset from the UCI Machine Learning Repository and is ready to use for training and evaluation.

The dataset includes clinical attributes such as:

- age
- sex
- cp (chest pain type)
- trestbps (resting blood pressure)
- chol (serum cholesterol)
- fbs (fasting blood sugar)
- restecg (resting electrocardiographic results)
- thalach (maximum heart rate achieved)
- exang (exercise-induced angina)
- oldpeak (ST depression induced by exercise relative to rest)
- slope (slope of the peak exercise ST segment)
- ca (number of major vessels colored by fluoroscopy)
- thal (thalassemia status)
- target (target class)

## Repository structure

- [heart-disease.csv](heart-disease.csv) — heart disease dataset used for model training and evaluation
- [heart-disease-classification.ipynb](heart-disease-classification.ipynb) — full analysis, EDA, model comparison, tuning, and evaluation
- [README.md](README.md) — project overview and usage guide
- [LICENSE](LICENSE) — project license

## Tools and libraries used

The notebook uses the Python data science stack, including:

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- scikit-learn

## Workflow

### 1. Exploratory data analysis

The notebook starts by examining the dataset shape, sample records, class distribution, missing values, and summary statistics. It explores the relationship between heart disease and key variables such as:

- sex
- chest pain type
- age
- maximum heart rate

This is used to understand patterns in the data before modeling.

### 2. Data visualization

The project includes several visualizations, such as:

- count plots of disease/no-disease outcomes
- bar charts comparing disease frequency by sex
- scatter plots of age versus maximum heart rate
- chest pain type vs target distribution
- correlation heatmap

These plots help identify which attributes most strongly relate to the target variable.

### 3. Model selection

The notebook compares several classification algorithms, including:

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Random Forest Classifier

A simple function is defined to train each model and compare their accuracy on the test set.

### 4. Hyperparameter tuning

To improve model performance, the notebook applies:

- RandomizedSearchCV
- GridSearchCV

This is done for both Logistic Regression and Random Forest models to search for stronger parameter combinations.

### 5. Evaluation and metrics

The tuned classifier is evaluated using:

- ROC curve
- AUC score
- confusion matrix
- classification report
- precision
- recall
- F1-score
- cross-validation metrics

The notebook also computes cross-validated accuracy, precision, recall, and F1 across 5 folds.

### 6. Feature importance

After fitting a Logistic Regression model, the notebook inspects the model coefficients to understand which features contribute most strongly to classification decisions. This helps interpret the model instead of treating it as a black box.

## Modeling strategy

The notebook follows a standard supervised learning process:

1. Split the dataset into features and target.
2. Create train and test subsets.
3. Train multiple machine learning models.
4. Compare their performance.
5. Tune hyperparameters to improve performance.
6. Evaluate the final model with classification metrics.
7. Interpret feature importance.

## Expected outcome

The project is designed to demonstrate that predictive modeling can identify heart disease risk using a patient’s clinical measurements. The notebook emphasizes both accuracy and interpretability, making the approach useful for understanding which features matter most in the prediction.

## How to run the project

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/heart-disease-classification.git
   cd heart-disease-classification
   ```

2. Create a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate
   ```

   On Windows:

   ```bash
   venv\Scripts\activate
   ```

3. Install dependencies:

   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

4. The dataset file [heart-disease.csv](heart-disease.csv) is already included in the repository root, so no separate download is required.

5. Open the notebook:

   ```bash
   jupyter notebook
   ```

6. Run the notebook cells in order to reproduce the analysis and model evaluation.

## Notes

- This project is intended as a learning and proof-of-concept machine learning workflow.
- It is not a medical diagnosis tool and should not be used as a substitute for professional clinical judgment.
- The notebook is structured for experimentation, so further improvements can include more advanced models, feature engineering, and deployment-ready pipelines.

## Future work

Possible next steps include:

- adding more data sources or additional patient features
- trying more advanced models such as XGBoost, Gradient Boosting, or SVM
- improving model interpretability
- building a small web or dashboard interface for predictions
- conducting deeper clinical analysis of predictive features

## License

This project is licensed under the [MIT License](LICENSE).

## Contributing

Contributions are welcome. If you would like to improve the notebook, add documentation, or suggest better modeling approaches, feel free to open an issue or submit a pull request.
