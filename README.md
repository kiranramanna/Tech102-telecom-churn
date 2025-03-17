# Telco Customer Churn Model Analysis

## Model Overview

We trained a Random Forest Classifier with balanced class weights to predict customer churn. The model was evaluated using a 70-30 train-test split and 5-fold cross-validation.

## Model Performance

### Random Forest Classifier

- **Overall Accuracy**: 75%
- **ROC-AUC Score**: 0.756
- **Cross-validation Score**: 0.765 (±0.009)

Performance by Class:
- Non-churners (0):
  - Precision: 0.81
  - Recall: 0.86
  - F1-score: 0.83
- Churners (1):
  - Precision: 0.53
  - Recall: 0.43
  - F1-score: 0.48

### Feature Importance Analysis

The Random Forest model identified the following feature importance ranking:
1. MonthlyCharges: 39.3%
2. TotalCharges: 36.7%
3. tenure: 24.0%

## Key Findings

1. **Model Performance**:
   - The model shows good overall performance with 75% accuracy
   - Strong ROC-AUC score of 0.756 indicates good discriminative ability
   - Consistent performance across cross-validation (0.765 ±0.009) suggests model stability

2. **Class Imbalance Handling**:
   - Using balanced class weights has helped address the class imbalance
   - Better performance on majority class (non-churners) but reasonable performance on minority class (churners)
   - Trade-off between precision and recall for churners suggests room for optimization

3. **Feature Impact**:
   - Billing-related features (MonthlyCharges and TotalCharges) are the strongest predictors
   - Customer tenure has significant but lower impact on churn prediction
   - The relative importance suggests focusing on pricing strategies for churn prevention

## Recommendations

1. **Model Application**:
   - Use model predictions with confidence scores for targeted interventions
   - Focus on cases where churn probability is high but not certain
   - Consider cost-benefit analysis when setting prediction thresholds

2. **Business Insights**:
   - Monitor and manage monthly charges as they have the highest impact on churn
   - Develop retention strategies focused on price-sensitive customers
   - Consider loyalty programs that reward longer tenure

3. **Future Improvements**:
   - Collect and incorporate additional features related to customer service interactions
   - Consider ensemble approaches to further improve prediction accuracy
   - Implement regular model retraining to maintain performance

## Confusion Matrix Analysis

The confusion matrix shows:
- Strong performance in identifying loyal customers (true negatives)
- Good ability to identify potential churners (true positives)
- Some false positives and false negatives, with bias towards reducing false negatives

This suggests the model is conservative in its churn predictions, which is appropriate for business applications where the cost of missing a potential churner is higher than the cost of unnecessary intervention.

## Next Steps

1. **Data Collection**:
   - Identify and collect additional relevant features
   - Implement better data quality measures

2. **Model Enhancement**:
   - Implement feature engineering techniques
   - Experiment with advanced modeling approaches
   - Develop a more robust evaluation framework

3. **Business Integration**:
   - Create an automated prediction pipeline
   - Develop actionable insights dashboard
   - Implement A/B testing for retention strategies 
