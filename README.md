# Bank Customer Complaints Classification

## Executive Summary

This project uses Natural Language Processing (NLP) to streamline customer complaint classification, reducing the time and complexity of complaint submission. By deploying an NLP model that automatically categorizes complaints based on content, the system eliminates the need for extensive questions or options, enhancing user experience with a simple interface.

We trained and evaluated various models, including Multinomial Naive Bayes, Support Vector Machine (SVM), Logistic Regression, Random Forest, and ExtraTrees, ultimately selecting the transformer-based BERT model for deployment. BERT demonstrated strong performance, achieving a Macro F1-score of 0.85, Weighted F1-score of 0.89, and an accuracy of 89%, providing balanced and reliable classification across complaint categories.

Deployed on Hugging Face with a Streamlit interface, the solution allows customers to input complaint text and contact details, which the BERT model then categorizes. Notifications are sent through Africastalking’s SMS API to both the customer and relevant support teams, ensuring immediate updates.

Future improvements recommended include implementing a feedback loop for continuous retraining, optimizing specific complaint types, and expanding notification channels, further enhancing the system’s accuracy, adaptability, and responsiveness.

## Project Overview


## Business Understanding


## Data understanding


## Data Exploration & Preparation

The initial data examination involved removing unnecessary columns and handling missing values in the narrative field. We identified 37,735 duplicate entries but retained them, as removing duplicates negatively impacted model performance. Class distribution analysis revealed a notable imbalance, especially in the credit reporting category, which was addressed through stratified splits and later SMOTE. A text length analysis showed a right-skewed distribution, with most narratives under 1,000 characters, aligning with typical complaint lengths.

The data preparation process involved comprehensive preprocessing and transformation steps to ensure clean, consistent, and usable data for modeling. During **data preprocessing**, text was standardized by converting it to lowercase, removing special characters and numbers, and handling whitespace. Tokenization split the text into individual words, while stop word removal filtered out common but uninformative words. Lemmatization reduced words to their root forms, enhancing the model’s ability to recognize related terms as a single concept. This preprocessing pipeline produced a well-processed `cleaned_narrative` column, ready for numerical feature extraction.

For **data transformation**, we split the data into training and testing sets with stratified sampling to maintain class balance. The text was then vectorized using TF-IDF to represent words as weighted features, capturing term importance. Finally, MinMax scaling was applied to standardize the feature values, resulting in `X_train_scaled` and `X_test_scaled` datasets optimized for model training and evaluation.


## Model Training, Evaluaton, Improvement & Selection

We trained a series of baseline models, including Multinomial Naïve Bayes, Support Vector Machine (SVM), Logistic Regression, and Random Forest, to identify the most effective method for classifying customer complaints. Model evaluation focused on classification report metrics—accuracy, precision, recall, and F1-score for each class—with a particular emphasis on **Macro F1-score** and **Weighted F1-score**. Macro F1 provided an equal-weighted average across all classes, aligning with our goal to treat each complaint category equally, while Weighted F1 accounted for class imbalance by assigning more weight to larger classes, offering a broader perspective on model performance.

For Model Improvement, we started by tuning the Random Forest model to enhance performance through parameter adjustments. We then applied SMOTE (Synthetic Minority Over-sampling Technique) to balance the dataset and retrained both a Random Forest and an ensemble ExtraTrees model on the resampled data, comparing their results with the tuned model. Finally, we explored a transformer-based model, **BERT**, which showed strong suitability for text classification tasks due to its deep language understanding. After evaluating performance across all metrics, we selected BERT as the most suitable model for deployment since it achieved robust accuracy and balanced performance across all complaint categories and for its appropriateness in natural language processing tasks.

## Deployment and Application


## Conclusion and Recommendations

