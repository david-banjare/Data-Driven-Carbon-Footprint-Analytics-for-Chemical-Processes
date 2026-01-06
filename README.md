# Data-Driven Carbon Footprint Analytics for Chemical Processes

## Overview
This project focuses on analyzing and predicting **carbon intensity
(CO₂ emissions per capita)** using global energy, fossil fuel, and
economic data. The objective is to identify the most important drivers
of emissions and build reliable, interpretable machine learning models
that align with established physical and economic theory.

The work was carried out as part of the **WiDS Winter Project**, with an
emphasis on clean data processing, robust modeling, and meaningful
interpretation rather than black-box prediction.

---

## Dataset
- **Source:** Our World in Data (OWID) – CO₂ and Greenhouse Gas Emissions  
- **Coverage:** Global, multi-country, multi-year  
- **Link:** https://github.com/owid/co2-data  

The dataset contains a wide range of emissions, energy, and economic
indicators. For this study, only variables directly relevant to carbon
intensity were selected to avoid redundancy and data leakage.

---

## Problem Statement
Carbon emissions are driven by a combination of energy consumption,
economic activity, and population dynamics. Understanding **which
factors matter most** and **how they interact** is essential for
developing effective climate mitigation strategies.

This project aims to:
- Predict CO₂ emissions per capita using data-driven methods
- Compare linear and non-linear regression models
- Identify the dominant contributors to carbon intensity
- Interpret model behavior in a physically meaningful way

---

## Methodology
The analysis follows a structured data science workflow:

1. **Data Cleaning and Selection**
   - Relevant feature selection based on domain knowledge
   - Handling missing values using interpolation, median imputation,
     and physically justified zero assumptions
   - Removal of redundant and highly correlated variables

2. **Feature Engineering**
   - Log-transformation of skewed variables
   - Feature scaling where appropriate
   - Train–test split to evaluate generalization performance

3. **Modeling**
   - Linear Regression (baseline)
   - Random Forest Regressor
   - Gradient Boosting Regressor (final model)

4. **Evaluation**
   - Root Mean Squared Error (RMSE)
   - Coefficient of Determination (R²)
   - Predicted vs Actual diagnostic plots

5. **Interpretation**
   - Feature importance analysis
   - SHAP-based explanations for the final model

---

## Results
### Model Performance

| Model | RMSE | R² |
|------|------|----|
| Linear Regression | 0.31 | 0.89 |
| Random Forest | 0.13 | 0.98 |
| Gradient Boosting | **0.12** | **0.98** |

Gradient Boosting achieves the best performance, explaining over **98% of
the variance** in carbon intensity and outperforming both the linear
baseline and Random Forest.

### Key Drivers of Carbon Intensity
Feature importance and SHAP analysis consistently identify:

1. **Energy consumption per capita** (dominant factor)
2. Population
3. Fossil fuel–specific emissions (oil, coal, flaring)
4. GDP (secondary, indirect role)

i.e 
- energy_per_capita
- oil_co2
- population
- coal_co2
- gdp

These results are consistent with established emissions theory,
including the **Kaya identity**, confirming that the model learns
physically meaningful relationships rather than spurious correlations.

---

## Interpretation and Insights
- Energy consumption per capita overwhelmingly drives CO₂ emissions per
  person.
- Non-linear models are necessary to capture threshold effects and
  interactions between variables.
- Economic growth alone does not directly increase emissions unless it
  is accompanied by energy-intensive activity.
- Model explanations align closely with real-world emissions behavior,
  increasing confidence in the results.

---

## Tools and Libraries

- Python
- pandas, numpy
- scikit-learn
- matplotlib, seaborn
- SHAP
- Jupyter Notebook

## Conclusion

This project demonstrates that carbon intensity can be modeled
accurately and interpretably using a small set of well-chosen features.
The results highlight the central role of energy consumption in driving
emissions and provide a strong foundation for further policy- and
scenario-based analysis.

## Future Work

1.Time-series modeling of emissions trends

2.Sector-wise emissions decomposition

3.Energy transition and policy scenario analysis

## Author
David Banjare
WiDS Winter Project – Data Science
