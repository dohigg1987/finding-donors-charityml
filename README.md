# Finding Donors for CharityML

**Author:** Dennis O'Higgins

Supervised learning project that predicts whether an individual earns more than $50,000 a year from 1994 U.S. Census data, so that the fictional charity CharityML can target its fundraising letters at the people most likely to donate.

The project files are in the [`finding_donors`](finding_donors) folder:

| File | Contents |
|---|---|
| `finding_donors.ipynb` | Completed notebook with all code executed and all questions answered |
| `report.html` | HTML export of the notebook |
| `census.csv` | Project dataset (45,222 records) |
| `visuals.py` | Supplementary plotting code provided with the project |

## Summary of results

| Model | Test accuracy | Test F-score (beta = 0.5) |
|---|---|---|
| Naive predictor (always ">50K") | 0.2478 | 0.2917 |
| Gaussian Naive Bayes | 0.5977 | 0.4209 |
| Logistic Regression | 0.8417 | 0.6826 |
| AdaBoost (default) | 0.8483 | 0.7029 |
| AdaBoost (tuned with GridSearchCV: 400 estimators, learning rate 1.5) | **0.8570** | **0.7227** |
| Tuned AdaBoost on the top 5 features only | 0.8495 | 0.7127 |

The five most important features found by AdaBoost are capital-gain, being married to a civilian spouse, years of education, age and capital-loss.

## Running the notebook

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
jupyter notebook finding_donors/finding_donors.ipynb
```
