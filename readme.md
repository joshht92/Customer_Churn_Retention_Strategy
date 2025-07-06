# Customer Retention Optimization Strategy with Churn Prediction

This repository contains a comprehensive analysis and optimization framework for targeted customer retention in a telecommunications context. Leveraging machine learning and optimization techniques, I predict customer churn risk, segment customers into actionable groups, and select retention targets under budget constraints to maximize profitability.

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
├── data/                           # Store raw or cleaned datasets
│   └── Telco-Customer-Churn.csv
├── scripts/                        # Your main R scripts
│   └── Customer_Churn_Final.R
├── reports/                        # Reports and outputs
│   └── Customer_Churn_Report-short.pdf
├── README.md                       # Project overview and instructions
└── .gitattributes                  # Git attribute settings
```

## Usage

R code is organized to follow the analysis workflow:

1. **Exploratory Data Analysis**: Examines summary statistics and initial patterns.
2. **Churn Modeling**: Trains and evaluates classification models.
3. **Threshold Analysis**: Explores trade-offs and selects a classification threshold.
4. **Customer Segmentation**: Uncovers behavioral clusters via K-means.
5. **Retention Optimization**: Formulates and solves a knapsack problem under budget.
6. **Results & Report**: Compiles findings and generates the final PDF report.

In the R code, execute each line sequentially to reproduce the analysis and update parameters as needed.

## Data

- **telco\_customer\_churn.csv**: Contains customer demographics, subscription details, service usage, financials, and churn indicator.

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

