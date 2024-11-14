# Bank Customer Complaints Classification

## Executive Summary

This project uses Natural Language Processing (NLP) to streamline customer complaint classification, reducing the time and complexity of complaint submission. By deploying an NLP model that automatically categorizes complaints based on content, the system eliminates the need for extensive questions or options, enhancing user experience with a simple interface.

We trained and evaluated various models, including Multinomial Naive Bayes, Support Vector Machine (SVM), Logistic Regression, Random Forest, and ExtraTrees, ultimately selecting the transformer-based BERT model for deployment. BERT demonstrated strong performance, achieving a Macro F1-score of 0.85, Weighted F1-score of 0.89, and an accuracy of 89%, providing balanced and reliable classification across complaint categories.

Deployed on Hugging Face with a Streamlit interface, the solution allows customers to input complaint text and contact details, which the BERT model then categorizes. Notifications are sent through Africastalking’s SMS API to both the customer and relevant support teams, ensuring immediate updates.

Future improvements recommended include implementing a feedback loop for continuous retraining, optimizing specific complaint types, and expanding notification channels, further enhancing the system’s accuracy, adaptability, and responsiveness.

## Project Overview


## Business Understanding


## Data understanding


## Data Exploration


## Data Preprocessing


## Data Transformation


## Model Training


## Model Evaluation


## Model Improvement


## Model Selection


## Deployment and Application


## Conclusion and Recommendations

