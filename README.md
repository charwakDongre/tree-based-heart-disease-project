# Heart Disease Prediction with Tree-Based Models

This project uses Decision Trees and Random Forests to predict the presence of heart disease based on a set of patient attributes. The analysis demonstrates the power of tree-based models, the concept of overfitting, and how ensemble methods like Random Forests can lead to more accurate and robust results. The entire workflow is documented in the accompanying Jupyter Notebook.

---

## The Dataset

The project uses the `heart.csv` dataset, which contains 13 clinical features of patients, along with a target variable indicating the presence (1) or absence (0) of heart disease.

---

## Project Workflow & Key Concepts

### 1. Single Decision Tree Classifier
A single Decision Tree was initially trained to classify patients.

- **Overfitting Analysis**: We first trained a "full" decision tree with no depth restrictions. This model achieved **100% accuracy on the training data** but a significantly lower accuracy on the unseen test data. This large gap is a classic sign of **overfitting**, where the model learns the noise in the training data instead of the underlying patterns.
- **Pruning**: To combat overfitting, a "pruned" tree was trained by setting a `max_depth=4`. This resulted in a model that generalized better, although its raw accuracy on this specific test set was lower.

### 2. Random Forest Classifier
To improve performance and reliability, a Random Forest model was trained.

- **Ensemble Power**: A Random Forest is an **ensemble** of multiple decision trees. By averaging the predictions of a "forest" of trees, it produces a more accurate and stable result. Our Random Forest model achieved a **test accuracy of 98%**, outperforming the single decision tree.

- **Feature Importance**: An advantage of Random Forests is their ability to calculate feature importances. This analysis revealed that features like **chest pain type (`cp`)**, **number of major vessels (`ca`)**, and **thalassemia type (`thal`)** were the most influential predictors in diagnosing heart disease.

### 3. Robust Evaluation with Cross-Validation
To ensure our evaluation was reliable and not just a result of a lucky train-test split, we used **5-fold cross-validation**.

- **Confirmation**: The cross-validation results confirmed our findings, showing that the **Random Forest (mean accuracy of ~99.7%)** was significantly more accurate and consistent than the pruned Decision Tree (mean accuracy of ~83.4%).

---

## How to Run the Code
1. Ensure you have Python and Jupyter Notebook installed.
2. Clone this repository to your local machine.
3. Install the required libraries:
   ```bash
   pip install pandas numpy scikit-learn matplotlib seaborn
