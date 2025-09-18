# Spring-Health-Predictive-Analytics
Spring Health Predictive Analytics: Safeguard Adolescent Mental Health in the Era of Social Media

## Abstract
Social media, despite its benefits, has created a digital environment where users can
inadvertently become trapped in unhealthy behavioral patterns. Anecdotal evidence highlights
individuals spending hours scrolling aimlessly through social media feeds, often at the expense
of real-world relationships and personal well-being. This behavior raises critical questions: Is
this indicative of underlying mental health issues? Could predictive analytics offer a means to
intervene before these issues escalate?

## Motivation
Research supports the connection between social media usage and mental health deterioration.
Studies have linked new media screen activities to increased rates of depression and suicide
among adolescents, a trend that has drawn significant attention from healthcare professionals and
policymakers. The 2023 Surgeon General’s advisory emphasized the need for technology
companies to improve data transparency and develop tools to mitigate these risks. Major
depressive episodes in adolescents in the United States have risen alarmingly from 8.7% in 2005
to 11.3% in 2014, with social media exposure cited as a contributing factor. This call to action
prompted the project team to explore how artificial intelligence can contribute to addressing this
societal issue.

The team partnered with SpringHealth– a New York-based mental health firm– to tackle the
challenge of predicting mental health deterioration from social media exposure. By developing a
machine learning-driven predictive model, the project aims to guide SpringHealth in identifying individuals at risk and crafting interventions that are both impactful and profitable. The solution
integrates survey-based insights into a decision framework that not only supports mental health
care but also aligns with SpringHealth’s business objectives, including its pursuit of federal
funding opportunities. Through this initiative, the team sought to bridge the gap between
academic innovation and real-world application, demonstrating how predictive analytics can be a
powerful tool in safeguarding mental health in the era of social media.

SpringHealth has recognized the urgent need to address this growing public health concern.
Known for its innovative and clinically validated Employee Assistance Programs (EAPs),
SpringHealth employs precision mental health solutions to provide personalized care to
employees. While its platform is designed to support employee well-being, it currently lacks the
capability to analyze social media patterns and predict their potential mental health implications.
This gap presents an opportunity to leverage predictive analytics to enhance SpringHealth’s
offerings, ensuring early identification and intervention for at-risk individuals.

In response to this challenge, a team of graduate students at GW School of Business developed a
prototype predictive analytics solution that integrates survey data with machine learning models.
This solution not only aligns with SpringHealth’s mission but also positions the company to
secure potential federal contracts, such as with the Substance Abuse and Mental Health Services
Administration (SAMHSA).

## Business Decision Strategy
The primary objective of the business decision strategy is to optimize Spring Health’s
interventions by predicting the mental health deterioration risk among social media users. The
strategy integrates machine learning predictions with cost-benefit analyses to identify
participants at risk, maximize profitability, and inform decision-making for incentivization
campaigns.

The GWU team adopted a multi-model approach to address the complexities of mental health
predictions. Three distinct sets of models were trained to achieve specific goals:

1. Prediction of mental health risk (Pr(X)): Four classifiers—Logistic Regression, Support
Vector Machine (SVM), Decision Tree, and Neural Network—were trained to estimate the
probability of a participant being affected by mental health issues due to social media usage.
Based on ROC AUC, the best model was selected.

2. Valuation of incentivizing participants (Vi(X)): Linear Regression was used to calculate
the likelihood of a participant reducing social media usage when incentivized.

3. Valuation of not incentivizing participants (Vni(X)): Another Linear Regression model
estimated the increase in sleep disorder scores when participants were not incentivized.

## Key Metrics
• Drop in Social Media Usage (Vi(X)): An engineered feature representing the value of
incentivization, calculated as the deviation of a participant’s social media usage from the
population mean.

• Increase in Sleep Issues (Vni(X)): A proxy for the consequences of not incentivizing,
derived from survey data on sleep disorders.

The Expected Benefit formula combines these predictions:

<table>
<tr>
<td style="border:1px solid black; padding:8px;">
<h4>Expected Benefit = Pr(X) × Vi(X) + (1−Pr(X)) × Vni(X)</h4>
</td>
</tr>
</table>

A decision to incentivize is made if the expected benefit exceeds a predefined threshold,
calculated as:

<table>
<tr>
<td style="border:1px solid black; padding:8px;">
<h4>—V_ni(X) / (V_ni(X) - V_i(X))</h4>
</td>
</tr>
</table>

## Cost-Benefit Framework
To quantify the economic impact of interventions, the team developed a cost-benefit matrix.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/2d3cad7d4249ee92b4791607f21763e4f38bf80c/Auxiliary/Confusion-Matrix-Flow.png" width="800" />

  Figure 1: Confusion Matrix (EPM) flow

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/2d3cad7d4249ee92b4791607f21763e4f38bf80c/Auxiliary/Cost-Benefit-Matrix.png" width="800" />

The matrix ensures that every prediction is evaluated for its financial implications, enabling Spring Health to make informed decisions.

## Expected Profit Analysis
Building on the cost-benefit framework, the GWU team proposed an Expected Profit formula:

<table>
<tr>
<td style="border:1px solid black; padding:8px;">
Expected Profit = p(P) * [ TPR<sub>E</sub> * V(TP)<sub>C</sub> + FNR<sub>E</sub> * V(FN)<sub>C</sub> ] + p(N) * [ TNR<sub>E</sub> * V(TN)<sub>C</sub> + FPR<sub>E</sub> * V(FP)<sub>C</sub> ]
</td>
</tr>
</table>



Where:

• p(P) and p(N) are the class priors for positive and negative cases.

• TPR<sub>E</sub>, FPR<sub>E</sub>, FNR<sub>E</sub>, TNR<sub>E</sub> are rates from the Expected Probability Matrix (EPM), built on
Expected Benefit and Cost-Benefit matrix.

• V(TP)<sub>C</sub>, V(FN)<sub>C</sub>, V(TN)<sub>C</sub>, V(FP)<sub>C</sub>, are class-specific business values. Merely calculating the
Expected Profit for all objects in X_Test is insufficient for Spring Health to fully evaluate the
impact of their intervention campaign. While we have not plotted Profit Curves—typically used
to visualize the relationship between expected profit and the percentage of test instances—such
visualizations could provide valuable insights. These curves would enable Spring Health
management to identify what percentage of test set observation aligns best with their
profitability objectives and maximizes campaign effectiveness.

## Data Description
We collected the raw dataset from Kaggle which contains responses from individuals regarding
their social media usage and mental health status. The key columns in the dataset include:

1. Timestamp: The date and time when each survey was completed.
2. Age: The respondent's age (numeric values).
3. Gender: The respondent's gender (e.g., Male, Female).
4. Relationship Status: The respondent's relationship status (e.g., Single, In a relationship).
5. Occupation Status: The current occupation status of the respondent (e.g., University
Student).
6. Organizational Affiliation: Type of organizations the respondent is affiliated with (e.g.,
University).
7. Use of Social Media: Whether the respondent uses social media (Yes/No).
8. Common Social Media Platforms: Platforms the respondent uses regularly (e.g.,
Facebook, Twitter, Instagram).
9. Average Time on Social Media: Average time spent on social media daily (e.g.,
Between 2 and 3 hours, More than 5 hours).
10. Usage Without Specific Purpose: Frequency of using social media without a specific
purpose (Likert scale).
11. 10-20: Various questions evaluating mental health, sleep, and behaviors related to social
media usage. These questions typically use a scale ranging from 1 to 5 to indicate
frequency or level of agreement.

## Data Cleaning and Preprocessing
The raw dataset was obtained from a survey regarding social media usage and its potential
effects on well-being. The dataset included multiple columns ranging from demographic
information to behavioral and psychological questions. Before doing analysis, we carried out a
thorough data cleaning and preprocessing phase to ensure the data was accurate and reliable.

1. Handling Missing Values: We began by checking for any missing values that could
impact our analysis. For important columns like age, gender, or social media usage,
missing entries were either imputed or removed based on their significance. For
categorical variables, we used the most common value (mode) for imputation, while for
numerical fields, we opted for the median where necessary.

2. Timestamp and Column Name Conversion: The Timestamp column, which showed
when each survey was completed, was converted from a string format to a standardized
datetime format. This made it easier to analyze trends over time and perform time-based
filtering. Also, we renamed the columns to make them more readable. Like change x2
Gender to gender.

3. Standardizing Categorical Data: To ensure consistency, we standardized categorical
responses like Gender, Relationship Status, and Occupation Status. This included
correcting variations in input values (e.g., "female" vs. "Female") through case
normalization. We also used one-hot encoding to prepare these categories for use in
machine learning models.

4. Encoding Survey Responses: Most of the survey responses were recorded on a Likert
scale (e.g., from 1 to 5), so we treated them as ordinal variables. We kept these values in
numerical form but standardized them to ensure they had similar distributions, which is
helpful when training models.

5. Feature Engineering: We also created new features to enhance the analysis. For
instance, we categorized the average time spent on social media into different levels (low,
medium, high) to make distinctions between user groups clearer. Additionally, we created
a Total Social Media Platforms Used feature by counting the number of platforms each
respondent mentioned.

6. Reassigning the Score: We also revised the scoring system for the self-esteem-related
questions. The original scoring system included some positive responses, which were
inconsistent with our focus on negative mental health impacts. So, we reassigned the
scores to only include responses reflecting negative mental health impacts. By excluding positive scores, the revised framework ensures that only responses reflecting negative
mental health impacts are included in the overall calculation.

7. Normalization and Scaling: For numerical features like Average Time on Social Media
and other scaled responses, we applied min-max normalization to scale the values
between 0 and 1. This helped ensure that all features contributed equally during the
modeling process.

8. Data Type Conversion: Finally, we reviewed the data types for each column and made
necessary conversions. For example, age was converted to an integer type, and
categorical features were converted to a category type to improve memory efficiency and
model performance.

By doing these data cleaning and preprocessing steps, we ensured that our dataset was consistent,
free of errors, and ready for meaningful analysis. This prepared data is ready for exploratory
analysis and modeling, which will build a solid foundation for gaining valuable insights.

## Data Visualization
We did several visualizations for the treated dataset to have a better understanding of the data.
According to this bar plot, in this data set, most people spend more than 5 hours on social
media.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Visualization-Average%20Time%20Spent%20on%20Social%20Media.png" width="800" />

According to this bar plot, 69.2% of the total population’s mental health of this data set are not
affected by using social media, and 30.8% of the total population’s mental health of this data are
affected by social media.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Visualization-Affected%20vs%20Not%20Affected.png" width="800" />

This bar plot shows a trend that ADHD scores will increase with the increasing amount of time
spent on social media.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Visualization-Mean%20ADHD%20Score%20by%20Time%20Spent.png" width="800" />

This bar plot shows a trend that Depression scores will increase with the increasing amount of
time spent on social media.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Visualization-Mean%20Depression%20Score%20by%20Time%20Spent.png" width="800" />

This heatmap emphasizes which variables are most closely related. For instance,
Depression_Scaled_Score and Anxiety_Scaled_Score stand out as critical indicators with strong
interrelationships and significant links to other variables, such as time spent on social media. The clustering of certain variables, like Anxiety_Scaled_Score, Depression_Scaled_Score, and
ADHD_Scaled_Score, suggests overlapping effects on overall mental health score.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/HeatMap-1.png" width="800" />

According to this heatmap, variables such as Depression_Scaled_Score, Anxiety_Scaled_Score,
and Avg_Time_SM_Num emerge as strong predictors of whether individuals are affected by
social media.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/HeatMap-2.png" width="800" />

## Models
In our project, we explored several machine learning models to analyze the relationship between
social media usage and mental health score. We selected Affected as our target variable, and
selected other important variable to predict our target variable.,

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Selected%20Attributes.png" width="800" />

## Linear Regression
According to the model summary, variables like Social_Media_UserYes(Coefficient: -0.0688,
p-value: 0.024), and ADHD_Q1 (Coefficient: 0.2682, p-value < 2e-16) are statistically
significant variables. Also, variables like Num_of_Platforms, and Depression_Scaled_Score are
insignificant variables because their p-value are larger than 0.05.
The Multiple R-squared value is 0.9741 which indicates that approximately 97.41% of the
variance in the outcome variable is explained by the predictors.
The Adjusted R-squared of 0.9719 reflects the proportion of variance explained, adjusted for the
number of predictors. This high value signifies an excellent fit.
Also, The F-statistic is 450.2, with a p-value < 2.2e-16, which means that the model is
statistically significant.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/LR-Model-Summary.png" width="800" />

## Decision Tree
We started with a Decision Tree model to identify the key features that contribute to mental
health scores. Decision Trees are easy to interpret and provide a visual representation of how
decisions are made based on different features.
The decision tree was trained using cross-validation to reduce the risk of overfitting and improve
generalizability. Cross-validation involves splitting the dataset into multiple subsets and
training/testing the model on these splits to ensure consistency in performance.
The Decision Tree Model highlighted Depression_Scaled_Score, Anxiety_Scaled_Score, and
ADHD_Scaled_Score as the most significant features influencing well-being. This helped us
understand which aspects of mental health played the largest role in predicting mental health
scores.

Also, The decision paths provided a clear explanation of how combinations of features could
lead to different predictions. For example, higher scores in Depression_Scaled_Score often led to
negative mental health scores.
However, The heavily skewed class suggests that certain combinations of features lead to strong
classification biases.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Decision%20Tree.png" width="800" />

## Logistic Regression
Logistic Regression was chosen to assess the linear relationships between the features and
well-being outcomes. It is a commonly used model for binary classification problems and
provides insights into the significance of each feature.
Our Logistic Regression Model was also trained with cross-validation to ensure robustness.
Logistic Regression assumes a linear relationship between the input features and the log-odds of
the output.
According to the summary of the Logistic Regression Model provided by RapidMiner, we found
key features included Depression_Scaled_Score, Anxiety_Scaled_Score, and
Self_Esteem_Scaled_Score, because their p-values are all less than 5%. Each feature's
coefficient indicated its impact on the likelihood of a particular outcome. For example, a high
Depression_Scaled_Score significantly increased the probability of a negative mental health
score.
The Logistic Regression model achieved an Area Under the Curve (AUC) of 1.0 and a logloss of
6.24E-5, indicating excellent discriminatory power. This suggests that the model was able to
accurately differentiate between positive and negative well-being outcomes.

<img src="https://github.com/arnab-raychaudhari/Spring-Health-Predictive-Analytics/blob/ecdad085b1fa1f03d2672854204cc9a69f79f7f2/Auxiliary/Logistic%20Regression%20Output.png" width="800" />

