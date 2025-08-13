## Tree Survival Prediction

### Project Overview

This project aims to predict the **survival outcome of planted trees** based on a diverse set of environmental and biological factors. By analyzing features such as tree species, light conditions, soil type, and biological metrics, the goal is to develop a machine learning model that can forecast whether a tree will survive. This has applications in forestry, conservation, and ecological restoration.

-----

### Technical Highlights

  * **Dataset**: [Kaggle - Tree Survival Prediction](https://www.kaggle.com/datasets/yekenot/tree-survival-prediction)
  * **Size**: 2783 entries, 24 columns
  * **Key Features**:
      * Species, Light\_ISF, Light\_Cat, Core, Soil, Adult, Sterile, Conspecific, Myco, SoilMyco, AMF, EMF, Phenolics, Lignin, NSC, Census, Time, Event.
  * **Approach**:
      * Data Cleaning: Dropped `No` and `Tree_ID` (if present) as they are unique identifiers. Mapped the `Alive` and `Harvest` columns from 'X' to 1 and `NaN` to 0. Filled missing values in `EMF` with the mean. The `Event` column's single null was also handled.
      * Exploratory Data Analysis: Histograms, Boxplots, and a heatmap were used for visualization to understand data distributions and correlations.
      * Label Encoding: Applied to all columns, including numerical ones and the target 'Alive'.
      * Handling Class Imbalance with `SMOTETomek` (a combination of oversampling and undersampling) on the training data. This is crucial as the original dataset is highly imbalanced in its `Alive` and `Harvest` categories.
      * Binary Classification: The target variable `Alive` indicates survival (`1`) or death (`0`).
      * Models Used:
          * Logistic Regression, Ridge Classifier, SVC, Random Forest, XGBoost, AdaBoost, Gradient Boosting, Bagging, Decision Tree.
  * **Best Accuracy**:
      * 100% with Ridge Classifier, XGBoost, Random Forest, AdaBoost, Gradient Boosting, Bagging, and Decision Tree.
      * 99.6% with Logistic Regression.
      * The extremely high accuracies for most models suggest that the features provide very strong discriminative power for tree survival, or that there may be a data leakage issue.

-----

### Purpose and Applications

  * Enable foresters and conservationists to **predict the survival rate of planted trees**.
  * Optimize tree planting strategies by identifying the most suitable conditions for different species.
  * Improve the efficiency of reforestation and ecological restoration projects.
  * Support data-driven decision-making in sustainable forestry and land management.

-----

### Installation

Clone the repository:

```bash
git clone https://github.com/BhaveshBhakta/Tree-Survival-Prediction-Using-ML.git
cd Tree-Survival-Prediction-Using-ML
```

Install the necessary libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn imbalanced-learn xgboost
```

-----

### Collaboration

We welcome contributions to improve the project. You can help by:

  * Investigating the very high accuracy for potential data leakage, which is a significant concern for such a predictive task.
  * Performing comprehensive hyperparameter tuning and cross-validation for all models to ensure robustness.
  * Exploring the impact of different feature selection or transformation techniques.
  * Adding explainability (e.g., SHAP or LIME) to understand which environmental factors are the most critical for tree survival.
