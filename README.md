<img width="1195" height="670" alt="image" src="https://github.com/user-attachments/assets/f99677a9-f6ae-4f3b-9fcd-cb743a73ab81" />
<img width="1176" height="634" alt="image" src="https://github.com/user-attachments/assets/441582bb-2d76-49b2-af63-8866480e2b6a" />
<img width="1157" height="600" alt="image" src="https://github.com/user-attachments/assets/9f5c824f-629e-4dd9-989d-9d49779e7084" />
<img width="1143" height="591" alt="image" src="https://github.com/user-attachments/assets/2967b25b-db3a-48b3-840e-785453555243" />
<img width="1171" height="606" alt="image" src="https://github.com/user-attachments/assets/330f4a69-df20-4549-aa55-7a575de53430" />
<img width="1164" height="616" alt="image" src="https://github.com/user-attachments/assets/8f990cca-cba7-4f9d-8e2f-2746c32d8010" />
<img width="1146" height="575" alt="image" src="https://github.com/user-attachments/assets/11a11656-31f0-4cfc-ab4f-7fcdfb97de68" />
<img width="1142" height="618" alt="image" src="https://github.com/user-attachments/assets/5d8bb7b2-e43a-444a-8b19-c0acfd84a092" />
<img width="1183" height="604" alt="image" src="https://github.com/user-attachments/assets/87faa3e8-f4c5-4fb5-895a-158f110116d7" />
<img width="1176" height="606" alt="image" src="https://github.com/user-attachments/assets/e76919fa-6130-4422-92b9-89dc9b1b353a" />


# HR Predictive Analytics — Employee Job Change Prediction

A Python-based machine learning project focused on employee job change intention, combining exploratory data analysis, data preparation, classification modeling, and model evaluation.

The project follows the CRISP-DM methodology to structure the analytical workflow, compare predictive models, and evaluate their ability to identify candidates who declare an intention to change jobs.

## Project Overview

Understanding job change intentions can support workforce analysis and talent management research.

This project investigates candidate characteristics associated with declared job change intentions and develops a supervised machine learning workflow to predict the target variable `procura_mudanca_emprego`.

**Main objectives:**
- Explore and understand the dataset.
- Assess data quality and prepare analytical features.
- Establish a baseline and compare classification models.
- Evaluate predictive performance using appropriate metrics.
- Document a reproducible end-to-end analytical workflow.

## Methodology

The project follows six stages inspired by the CRISP-DM methodology.

| Stage | Description |
|---|---|
| Business Understanding | Define the business problem, objectives, hypotheses, evaluation criteria, and limitations. |
| Data Understanding | Explore data quality, distributions, and relationships between variables. |
| Data Preparation | Prepare the data and establish training and test datasets. |
| Modeling | Train and compare classification algorithms against a baseline. |
| Evaluation | Assess model performance and examine classification errors. |
| Deployment | Demonstrate batch prediction and export analytical outputs. |

## Dataset

- **Number of observations:** 19,158
- **Target variable:** `procura_mudanca_emprego`
- **Training set:** 15,326 observations
- **Test set:** 3,832 observations

The dataset was provided for the course project. Its original upstream source, sampling methodology, and redistribution licence have not been independently established.

The target represents a declared intention to change jobs, not actual employee turnover. Results should therefore be interpreted within this scope.

## Modeling Approach

Four classification approaches were evaluated:

- Dummy Classifier — baseline
- Logistic Regression
- Decision Tree
- Random Forest

Model selection was based on the mean F1-score for the positive class across five-fold cross-validation on the training set, using a classification threshold of 0.50.

The test set was reserved for the final evaluation of the selected model.

## Results

### Cross-validation comparison

| Model | Mean F1-score |
|---|---:|
| Dummy Classifier | 0.000 |
| Logistic Regression | 0.466 |
| Decision Tree | 0.611 |
| **Random Forest** | **0.618** |

Random Forest achieved the highest mean F1-score across the evaluated models and was selected for further evaluation.

### Final test-set performance

| Metric | Score |
|---|---:|
| Recall | 0.746 |
| F1-score | 0.605 |
| ROC-AUC | 0.785 |

These results show that the selected model identifies a meaningful proportion of positive cases in the test set. Performance should also be considered alongside false positives, false negatives, class distribution, and the intended application.

The reported scores are experimental results and do not establish production readiness or real-world business impact.

## Technical Skills Demonstrated

- **Python** — analytical workflow and model development
- **Pandas** — data manipulation and preparation
- **Scikit-learn** — preprocessing, classification, cross-validation, and evaluation
- **Exploratory Data Analysis** — distributions, data quality, and feature exploration
- **Machine Learning** — baseline comparison and supervised classification
- **Model Evaluation** — F1-score, recall, and ROC-AUC
- **Jupyter Notebook** — documented analytical workflow
- **Data Visualization** — graphical exploration and presentation of findings

## Repository Structure

```text
hr-predictive-model-python/
├── README.md
├── requirements.txt
├── preparacao_rh.py
├── 01_P_business_understanding.ipynb
├── 02_P_data_understanding.ipynb
├── 03_P_data_preparation.ipynb
├── 04_P_modeling.ipynb
├── 05_P_evaluation.ipynb
└── 06_P_deployment.ipynb
```

The notebooks document the analytical workflow from business understanding to prediction and evaluation. Supporting datasets, generated outputs, and model artifacts can be maintained separately where appropriate.

## How to Run

### 1. Install Python

Install a compatible Python version and create a virtual environment if desired.

### 2. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook

```bash
python -m pip install jupyter
jupyter notebook
```

### 4. Execute the workflow

Run the notebooks in numerical order, from `01` to `06`.

The original dataset and any required supporting files must be available in the expected locations before execution.

## Limitations and Future Improvements

- Verify the original dataset source, representativeness, and permitted use.
- Evaluate generalization using independent datasets or different time periods.
- Investigate precision-recall trade-offs and alternative classification thresholds.
- Assess potential bias and the implications of candidate-level predictions in HR contexts.
- Improve reproducibility through automated tests, data validation, and documented dependencies.
- Explore additional models and compare performance using business-relevant evaluation criteria.

## Conclusion

This project demonstrates an end-to-end supervised learning workflow applied to an HR analytics problem, combining business understanding, exploratory data analysis, data preparation, model comparison, and evaluation.

Random Forest achieved the strongest cross-validation F1-score among the evaluated approaches, providing a basis for further investigation into predicting declared job change intentions.

---

*Python & Data Analytics Portfolio Project*
