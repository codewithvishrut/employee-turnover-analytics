# Employee Turnover Analytics

A machine learning project to predict and prevent employee attrition using HR data. Built as part of an initiative to help organizations identify at-risk employees and implement targeted retention strategies.

## Project Overview

Employee turnover is expensive - it costs companies thousands of dollars in recruitment, training, and lost productivity. This project uses historical HR data to build predictive models that can identify employees who are likely to leave, allowing HR teams to intervene proactively.

The analysis includes:
- Identifying key factors that contribute to employee turnover
- Clustering analysis to understand different types of departing employees
- Building and comparing multiple ML models
- Creating a risk-based framework for retention strategies

## Dataset

The dataset contains information about employees including:
- Satisfaction level
- Last performance evaluation score
- Number of projects handled
- Average monthly hours worked
- Years at the company
- Work accidents
- Promotions in last 5 years
- Department
- Salary level

**Source:** Modified from [Kaggle HR Analytics Dataset](https://www.kaggle.com/liujiaqi/hr-comma-sepcsv)

## Tech Stack

- **Python 3.8+**
- **Libraries:**
  - pandas, numpy - Data manipulation
  - matplotlib, seaborn - Visualization
  - scikit-learn - ML models and preprocessing
  - imbalanced-learn - SMOTE for class imbalance
  
## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/employee-turnover-analysis.git
cd employee-turnover-analysis

# Install required packages
pip install -r requirements.txt
```

### Requirements

Create a `requirements.txt` file with:
```
pandas>=1.3.0
numpy>=1.21.0
matplotlib>=3.4.0
seaborn>=0.11.0
scikit-learn>=1.0.0
imbalanced-learn>=0.8.0
jupyter>=1.0.0
```

## Usage

1. Place your HR data file (CSV format) in the project directory
2. Open the Jupyter notebook:
   ```bash
   jupyter notebook employee_turnover_analysis.ipynb
   ```
3. Update the data loading path in the first cell
4. Run all cells to perform the complete analysis

## Project Structure

```
employee-turnover-analysis/
│
├── employee_turnover_analysis.ipynb    # Main analysis notebook
├── README.md                           # Project documentation
├── requirements.txt                    # Python dependencies
├── data/                               # Data directory (not included)
│   └── HR_comma_sep.csv
└── outputs/                            # Generated plots and reports
    ├── correlation_heatmap.png
    ├── distribution_plots.png
    ├── kmeans_clusters.png
    ├── roc_curves.png
    └── confusion_matrices.png
```

## Analysis Pipeline

### 1. Data Quality Check
Validates data integrity and checks for missing values.

### 2. Exploratory Data Analysis
- Correlation analysis between features
- Distribution analysis of key metrics
- Relationship between workload and turnover

### 3. Clustering Analysis
K-means clustering identifies three distinct groups of departing employees:
- **Cluster 0:** Unsatisfied underperformers
- **Cluster 1:** Overworked high performers (burnout risk)
- **Cluster 2:** Satisfied employees who still left

### 4. Model Training
Three models trained with 5-fold cross-validation:
- Logistic Regression (baseline)
- Random Forest Classifier
- Gradient Boosting Classifier

Class imbalance handled using SMOTE upsampling.

### 5. Model Evaluation
Models compared using:
- ROC-AUC curves
- Confusion matrices
- Precision, Recall, F1-score

**Primary metric:** Recall - because missing an at-risk employee is more costly than a false alarm.

### 6. Risk-Based Retention Framework

Employees categorized into four risk zones:

| Risk Zone | Probability | Action Required |
|-----------|-------------|-----------------|
| 🟢 Safe | < 20% | Maintain engagement |
| 🟡 Low-Risk | 20-60% | Regular check-ins |
| 🟠 Medium-Risk | 60-90% | Immediate intervention |
| 🔴 High-Risk | > 90% | Urgent senior leadership involvement |

## Key Findings

Based on the analysis, main factors contributing to turnover:
- Employees with 2 or 7+ projects are at higher risk
- Low satisfaction combined with long hours indicates burnout
- Lack of recent promotions correlates with departures
- Department and salary level also play significant roles

## Results

The best performing model achieves:
- **ROC-AUC:** ~0.95+ (varies by dataset)
- **Recall:** High (prioritized to catch most at-risk employees)
- Successfully identifies 85-90% of employees who will leave

## Retention Strategies

Detailed, actionable strategies provided for each risk zone. High-risk employees require:
- Immediate manager escalation
- Compensation review
- Career development discussion
- Flexible work arrangements consideration

## Future Improvements

- [ ] Feature engineering with domain expertise
- [ ] Deep learning models (neural networks)
- [ ] Time-series analysis for temporal patterns
- [ ] Integration with real-time HR systems
- [ ] A/B testing of retention interventions
- [ ] Cost-benefit analysis of retention efforts

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, open an issue first to discuss proposed changes.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Dataset sourced from Kaggle
- Inspired by real-world HR analytics challenges
- Thanks to the open-source community for the amazing tools

## Contact

For questions or feedback, please open an issue or reach out via:
- GitHub: [@codewithvishrtu](https://github.com/codewithvishrut)
- Email: vishu06021998@gmail.com

---

⭐ If you find this project helpful, please consider giving it a star!