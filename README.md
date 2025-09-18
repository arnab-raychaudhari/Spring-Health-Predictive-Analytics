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

<h3>Expected Benefit = Pr(X) × Vi(X) + (1−Pr(X)) × Vni(X)</h3>

A decision to incentivize is made if the expected benefit exceeds a predefined threshold,
calculated as:

<h3>—V_ni(X) / (V_ni(X) - V_i(X))</h3>

## Cost-Benefit Framework
To quantify the economic impact of interventions, the team developed a cost-benefit matrix.

