# Customer Retention Optimization with Churn Prediction

This repository contains a comprehensive analysis and optimization framework for targeted customer retention in a telecommunications context. Leveraging machine learning and optimization techniques, we predict customer churn risk, segment customers into actionable groups, and select retention targets under budget constraints to maximize profitability.

## Table of Contents

- [Business Context](#business-context)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Data](#data)
- [Methodology](#methodology)
  - [Exploratory Data Analysis](#exploratory-data-analysis)
  - [Churn Prediction Model](#churn-prediction-model)
  - [Threshold & Trade-offs](#threshold--trade-offs)
  - [Customer Segmentation](#customer-segmentation)
  - [Retention Optimization](#retention-optimization)
- [Results](#results)
- [Future Work](#future-work)
- [License](#license)

## Business Context

In subscription-based industries, reducing customer churn directly impacts profitability by increasing customer lifetime value and improving marketing efficiency. This project addresses the challenge of identifying and retaining high-risk customers within a constrained budget using data-driven methods.

## Project Structure

```
├── data/                       # Raw and processed data files
│   └── telco_customer_churn.csv
├── notebooks/                  # Jupyter notebooks for each analysis step
│   ├── 1_eda.ipynb             # Exploratory data analysis
│   ├── 2_churn_model.ipynb     # Churn prediction modeling
│   ├── 3_threshold_analysis.ipynb
│   ├── 4_segmentation.ipynb
│   ├── 5_retention_optimization.ipynb
│   └── 6_results_and_report.ipynb
├── src/                        # Supporting Python modules
│   ├── data_processing.py
│   ├── modeling.py
│   └── optimization.py
├── reports/                    # Generated outputs and visualizations
│   └── Customer_Churn_Report.pdf
├── requirements.txt            # Python dependencies
└── README.md                   # Project overview (this file)
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/retention-optimization.git
   cd retention-optimization
   ```
2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Notebooks are organized to follow the analysis workflow:

1. **Exploratory Data Analysis**: `notebooks/1_eda.ipynb` examines summary statistics and initial patterns.
2. **Churn Modeling**: `notebooks/2_churn_model.ipynb` trains and evaluates classification models.
3. **Threshold Analysis**: `notebooks/3_threshold_analysis.ipynb` explores trade-offs and selects a classification threshold.
4. **Customer Segmentation**: `notebooks/4_segmentation.ipynb` uncovers behavioral clusters via K-means.
5. **Retention Optimization**: `notebooks/5_retention_optimization.ipynb` formulates and solves a knapsack problem under budget.
6. **Results & Report**: `notebooks/6_results_and_report.ipynb` compiles findings and generates the final PDF report.

Execute cells sequentially to reproduce the analysis and update parameters as needed.

## Data

- **telco\_customer\_churn.csv**: Contains customer demographics, subscription details, service usage, financials, and churn indicator.

> **Note**: Do not commit sensitive or proprietary data to the repository. Store large datasets externally if needed.

## Methodology

### Exploratory Data Analysis

- Summary statistics of demographics, tenure, charges, and churn distribution.
- Visualizations to highlight key patterns.

### Churn Prediction Model

- Comparison of Logistic Regression, Naïve Bayes, CART, and k-NN.
- Selection of Logistic Regression based on AUC and recall.
- Feature importance analysis.

### Threshold & Trade-offs

- F1-score vs. probability threshold.
- Precision–Recall and ROC trade-offs.
- Optimal threshold selection (≈0.25) for balancing recall and false positives.

### Customer Segmentation

- Use Elbow Method to determine K.
- K-means clustering and PCA visualization.
- Persona profiles for each segment.

### Retention Optimization

- Baseline heuristic versus budget-constrained knapsack model.
- Formulation of expected net benefit and cost constraints.
- Comparative ROI analysis.

## Results

- **Heuristic Approach**: Identified \~2,052 customers with a total expected profit of \$191,189 (ROI \~43.7%).
- **Knapsack Optimization**: Selected 1,349 customers under a \$250K budget with expected profit \$172,261 (ROI \~64.4%).
- Significant uplift in ROI by focusing on high-risk, high-value segments.

## Future Work

- **Customized Incentives**: Tailor offers by segment or individual risk.
- **Predicted CLV Integration**: Incorporate dynamic CLV predictions for prioritization.
- **Automation**: Deploy models and optimization as microservices for real-time use.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

