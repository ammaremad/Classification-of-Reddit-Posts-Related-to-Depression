# README

## Project Title: Analysis of Reddit Posts Related to Depression

### Overview
This project aims to analyze a dataset of Reddit posts to classify them based on the presence of depression-related content. The dataset consists of various features, including subreddit, title, body of the post, upvotes, creation time, number of comments, and a label indicating whether the post is normal (0) or depressed (1).

### Table of Contents
- [Objective](#objective)
- [Data Overview](#data-overview)
- [Data Preprocessing](#data-preprocessing)
- [Data Visualization](#data-visualization)
- [Feature Engineering](#feature-engineering)
- [Normalization](#normalization)
- [Model Development](#model-development)
- [Model Evaluation](#model-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)

### Objective
The primary goal of this project is to classify Reddit posts based on their emotional content, specifically identifying posts related to depression. 

### Data Overview
- **Dataset Size**: 2,470,778 entries and 8 columns.
- **Columns**:
  - `Subreddit`: The subreddit where the post was shared.
  - `Title`: The title of the post.
  - `Body`: The content of the post.
  - `Upvotes`: The number of upvotes received.
  - `Created UTC`: The time the post was created in UTC epoch time.
  - `Num Comments`: The total number of comments on the post.
  - `Label`: The target variable indicating normal (0) or depressed (1).

### Data Preprocessing
1. **Data Cleaning**: 
   - Dropped the unnecessary 'Unnamed: 0' column.
   - Handled missing values by filling in the 'Body' column with "No Content" and treating NaN values in 'Num_Comments' as 0.
   - Converted object data types to categorical for better handling and applied label encoding.

2. **Statistical Overview**: Provided statistical measures for numerical columns using the `describe()` function.

3. **Outlier Detection**: Identified and handled outliers using the Interquartile Range (IQR) method.

### Data Visualization
- **Histograms**: Displayed the distribution of upvotes and number of comments, revealing a right-skewed distribution.
- **Scatter Plot**: Illustrated the relationship between upvotes and number of comments, indicating no significant correlation.
- **Bar Chart**: Showed the number of posts per subreddit, highlighting a concentration of posts in a single subreddit.
- **Line Chart**: Analyzed the number of posts over time, revealing a spike in activity around 2017.

### Feature Engineering
- Created new columns for label encoding to retain original text for visualization.
- Evaluated the correlation between features and the target label, identifying 'Subreddit_encoded' as the most influential feature.

### Normalization
Scaled features to a common range using MinMaxScaler to prepare for model training.

### Model Development
- **Data Splitting**: Divided the dataset into training and testing sets (80% train, 20% test).
- **Machine Learning Models**:
  - **Logistic Regression**: Achieved an accuracy of 100%.
  - **Naive Bayes**: Also achieved 100% accuracy.
  - **Random Forest**: Reached 100% accuracy, confirming the robustness of the models.

### Model Evaluation
- **ROC Curve and AUC Score**: Evaluated the performance of the Logistic Regression model using ROC analysis.
- **Learning Curves**: Plotted learning curves for each model to assess underfitting and overfitting.

### Conclusion
All models performed exceptionally well, achieving 100% accuracy. The most influential feature was identified as 'Subreddit_encoded', warranting further investigation into its impact on the classification of depression-related content.

### Future Work
Further exploration could involve:
- Analyzing the content of posts to identify specific themes or language patterns associated with depression.
- Implementing more complex models or deep learning techniques to enhance classification performance.
- Investigating the temporal dynamics of posts and their correlation with external events or trends in mental health discussions online.

### Requirements
- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, plotly, scikit-learn, imbalanced-learn, xgboost

### Installation
To install the required libraries, run:
```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn imbalanced-learn xgboost
```

### Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/ammaremad/reddit-depression-analysis.git
   ```
2. Navigate to the project directory:
   ```bash
   cd reddit-depression-analysis
   ```
3. Run the analysis script:
   ```bash
   python analysis.py
   ```

