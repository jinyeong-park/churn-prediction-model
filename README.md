# SC Music Churn Prediction

## Executive Summary
This project develops a predictive model to identify SC Music customers at high risk of canceling their subscriptions, using three months of subscription and listening history data. By applying supervised learning techniques, including logistic regression and decision trees, the analysis uncovers key drivers of churn such as discount usage and music genre preferences. The final model achieves 85% accuracy in predicting cancellations, enabling targeted retention strategies that could reduce churn by up to 20% and increase customer lifetime value.

## Business Problem
SC Music is experiencing rising subscription cancellations, which directly reduce recurring revenue and hinder sustainable growth in the competitive music streaming market.  
This issue matters to stakeholders — artists depend on consistent listener engagement for royalty income, producers require stable audience data for content planning, and record labels rely on platform retention for successful artist promotion — ultimately affecting the entire music ecosystem.

The project answers the following key questions:  
- What are the strongest predictors of customer churn?  
- How can we effectively segment at-risk customers?  
- What data-driven interventions can meaningfully reduce cancellation rates?

## Methodology
Data was sourced from two main files:  
- Customer data (`sc_music_customers.csv`)  
- Listening history (`sc_music_listening_history.xlsx` – 505 session entries across multiple sheets)

Key features engineered and used include: subscription plan, discount status, number of listening sessions, percentage of pop music listened to, percentage of podcasts, and cancellation indicators.

A supervised binary classification approach was followed:  
1. Data cleaning & merging (handling missing values, joining datasets on Customer ID)  
2. Exploratory analysis (correlations, pairplots, genre distribution)  
3. Modeling progression:  
   - Baseline: Logistic Regression (~72% accuracy)  
   - Final: Tuned Decision Tree (85% accuracy via grid search)  

Performance was evaluated using accuracy, precision (0.82 for churn class), recall (0.78), and 5-fold cross-validation to ensure generalization.

## Skills Demonstrated
- **Technical / Programming**  
  Pandas data wrangling · Multi-sheet Excel reading with openpyxl · Seaborn & Matplotlib visualization · Jupyter Notebook workflow

- **Machine Learning & Data Science**  
  Feature engineering (genre percentages, session counts) · Binary classification · Hyperparameter tuning (GridSearchCV) · Correlation & feature importance analysis · Handling small/imbalanced datasets

- **Business & Analytical Thinking**  
  Translating model insights into retention strategies · Prioritizing high-impact features (discount, pop genre) · Stakeholder-oriented recommendation framing

- **Tools & Libraries**  
  Python 3.12 · Pandas · NumPy · Scikit-learn · Seaborn · Matplotlib · Jupyter Notebook

## Results & Business Recommendations
**Final Model Performance**  
- Accuracy: 85%  
- Precision (churn class): 0.82  
- Recall (churn class): 0.78  
→ 13 percentage point improvement over baseline

**Top Feature Insights**  
1. Discount usage → strongest positive correlation with churn (importance ~0.45)  
2. Number of sessions → strong negative correlation (more sessions = lower churn risk)  
3. Percent pop music → significant positive correlation with cancellation (~0.59)  
4. Podcast listening → near-zero relationship with churn

**Genre Insight**  
Customers with >60% pop music listening showed ~58% higher churn probability, likely tied to dissatisfaction with ads in the Basic (Ads) plan.

**Actionable Recommendations**

1. **Target Discounted Customers with Smart Upsell**  
   **Who**: Marketing Team  
   **How**: Query customers currently on discount → send personalized premium upgrade offers (e.g., 15% off first 3 months, highlight ad-free pop experience) within 30 days of discount start.

2. **Re-engage Low-Activity Users**  
   **Who**: Product / Growth Team  
   **How**: Identify users with <3 sessions/month → trigger automated, personalized playlist recommendations via push/email (focus on genre diversity) to increase session frequency.

3. **Launch Pop-Focused Retention Playlists**  
   **Who**: Content Curation Team  
   **How**: Flag users with >50% pop listening → automatically surface hybrid playlists (e.g., 70% pop + 30% podcasts/indie) in-app; run A/B tests to measure retention lift.

4. **Introduce Mid-Tier Plan for Pop Listeners**  
   **Who**: Pricing & Strategy Team  
   **How**: Pilot a $5.99 “Pop Plus” tier (limited ads, pop priority) targeted at Basic plan users with high pop consumption; measure 90-day retention vs control group.

5. **Build Early-Warning Churn Alerts**  
   **Who**: Customer Success / Data Team  
   **How**: Deploy model predictions to internal dashboard → trigger proactive outreach (e.g., 1-month free Premium trial) for customers with >70% predicted churn probability.

## Next Steps
- Collect larger historical dataset + real-time streaming events  
- Experiment with ensemble methods (Random Forest, XGBoost)  
- Deploy model as API for CRM integration  
- Run controlled experiments on top 2–3 recommendations to measure actual churn reduction & revenue impact

## Project Structure
