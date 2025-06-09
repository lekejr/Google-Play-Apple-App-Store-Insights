# Google Play & Apple App Store Analytics & Forecasting Dashboard Report

## Executive Summary

The objective is to develop a strategic, insight-driven dashboard that enhances decision-making in app performance, user engagement and revenue generation. This dashboard integrates predictive analytics, external datasets and critical KPIs to provide actionable recommendations. The final product enables executives to explore real-time insights and make data-driven strategic decisions.
![Screenshot (498)](https://github.com/user-attachments/assets/d6478db9-39e2-4c7f-9a02-8ad07961794b)

### Key Deliverables

- Google Play Store and Apple App Store dataset integration  
- Data Cleaning and Exploration  
- Predictive analytics on user engagement and market trends  
- Comparative insights for competitive benchmarking  
- Interactive Power BI dashboard  


## Overview of Raw Data & Data Cleaning Process

### Google Play Store Dataset

- **Total Apps**: 2,000,000  
- **Key Columns**: App Name, Category, Ratings, Installs, Revenue, Engagement Metrics  
- **Challenges**: Missing values, duplicate records, inconsistent data formats  
- **Cleaning Steps**: Standardization of columns, removal of duplicates, imputation of missing values  

### Apple App Store Dataset (External Dataset)

- **Total Apps**: 1,230,376  
- **Key Columns**: App Name, Category, Ratings, Reviews, Pricing, Developer Info  
- **Challenges**: Inconsistent formats, missing ratings, varying price structures  
- **Cleaning Steps**: Data normalization, handling null values, standardization of price and rating scales  


## Tools Used

- **Python (Pandas, NumPy)**: Data cleaning and exploration  
- **Power BI**: Data visualization and dashboard development  


## Key Performance Indicators (KPIs)

### Google Play Store KPIs

- **Total Number of Apps**: 2M  
  - DAX Measure: `COUNT(App_ID)`  
  - Why: Indicates the size of the Google Play Store ecosystem and competition level.  

- **Average App Rating**: 2.21  
  - DAX Measure: `AVERAGE(Rating)`  
  - Why: Reflects overall user satisfaction, highlighting potential quality issues.  

- **Total Revenue**: $235K  
  - DAX Measure: `SUM(Price)`  
  - Why: Useful for understanding the monetization potential of paid apps.  

- **Engagement Score**: 2.84K  
  - DAX Measure: `SUM(Reviews) / COUNT(App_ID)`  
  - Why: Higher engagement indicates better user interaction and potential retention.  

- **Retention Rate**: 1.50  
  - DAX Measure: `(Active Users / Total Installs)`  
  - Why: Low retention indicates users uninstalling apps quickly, requiring strategy changes.  

- **Top Revenue-Generating Categories**  
  - DAX Measure: `SUM(Revenue) by Category`  
  - Why: Identifies the most profitable app categories for investment.  

- **Most Installed Apps**  
  - DAX Measure: `TOPN(10, SUM(Installs))`  
  - Why: Helps benchmark popular apps and identify user trends.  

- **Trend Forecasting for Installs (Next 5 Years)**  
  - DAX Measure: Time-series regression model on `SUM(Installs)`  
  - Why: Predicts future growth for strategic planning.  

- **Free vs. Paid Apps Ratio**: 52.17% Free  
  - DAX Measure: `COUNT(Free Apps) / COUNT(Total Apps)`  
  - Why: Indicates prevailing monetization models in the store.  

- **Top Apps by Rating**  
  - DAX Measure: `TOPN(10, AVERAGE(Rating))`  
  - Why: Highlights best-rated apps, serving as a benchmark for quality improvement.  

### Apple App Store KPIs

- **Total Number of Apps**: 1.23M  
  - DAX Measure: `COUNT(App_ID)`  
  - Why: Shows the size of the Apple App Store ecosystem.  

- **Average App Rating**: 1.79  
  - DAX Measure: `AVERAGE(Rating)`  
  - Why: Indicates user sentiment towards Apple Store apps.  

- **Total Revenue**: $620K  
  - DAX Measure: `SUM(Price)`  
  - Why: Demonstrates revenue potential within Apple's store.  

- **Average Number of Installs**: 82.59K  
  - DAX Measure: `AVERAGE(Installs)`  
  - Why: Helps in comparing user adoption rates across platforms.  

- **Most Popular Categories**  
  - DAX Measure: `SUM(Revenue) by Category`  
  - Why: Determines which categories attract the most revenue.  

---

## Predictive Analytics & Forecasting

- **App Install Trends**: Forecasts for Google Play Store indicate a steady growth in installs over the next five years.  
- **User Engagement Analysis**: Apps with a high retention rate correlate with higher revenue.  

---

## Actionable Insights

### 1. Top 10 Categories by Revenue Generated
![image](https://github.com/user-attachments/assets/9bcd39e4-ace1-453f-9791-2751f592b2a8)

- DAX Measure: `SUM(Revenue) by Category`  
- Insight: Highlights the top 10 most profitable app categories.  
- Importance: Helps businesses prioritize investment in high-revenue categories.  

### 2. Comparing Ratings on Google Play vs. Apple App Store
![image](https://github.com/user-attachments/assets/05390de9-5201-4bb8-9408-ae6d08aa1293)

- DAX Measure: `AVG(Rating)`  
- Insight: Google Play Store apps tend to have higher average ratings.  
- Business Importance: Shows user perception differences between platforms.  

### 3. Top 5 App Categories with High Installs but Low Retention
![image](https://github.com/user-attachments/assets/acc6c868-e646-456c-b2f6-8e067bbd55ae)

- Formula: `SUM(Installs)` & `Retention Rate`  
- Insight: Some categories attract many downloads but fail to retain users.  
- Business Importance: Helps in refining app features and engagement strategies  

### 4. Install Trends & Forecast for the Next 5 Years
![image](https://github.com/user-attachments/assets/d6e1f7d0-1021-4473-a88a-f8963159b2c1)

- Formula: Time-series regression forecast on `SUM(Installs)`  
- Insight: Predicts future install growth trends.  
- Business Importance: Supports strategic planning and market positioning.  

### 5. Free App Ratio (Google Play vs. Apple)
![image](https://github.com/user-attachments/assets/d8a854cc-b540-4c4e-95f9-b8d048bb1d6d)

- Formula: `COUNT(Free Apps) / COUNT(Total Apps)`  
- Insight: Google Play has a higher percentage of free apps.  
- Business Importance: Indicates monetization strategies across platforms.  

### 6. Top 10 Apps by Rating
![image](https://github.com/user-attachments/assets/94328246-8adf-4594-8b55-ff7ec0b57a79)

- Formula: `TOPN(10, AVG(Rating))`  
- Insight: Displays the best-rated apps.  
- Business Importance: Highlights successful app attributes for benchmarking.  

### 7. Top 10 Most Engaged Apps
![image](https://github.com/user-attachments/assets/72cbef32-9701-4b94-bd28-b4151244219e)

- Formula: `SUM(Reviews) by App`  
- Insight: Identifies the apps with the highest user interaction.  
- Business Importance: Useful for analyzing market trends and customer loyalty.  

### 8. Average Age of Apps
![image](https://github.com/user-attachments/assets/bfed3ed4-ac18-4e50-8fe7-b136b3a2a0ea)

- Formula: `AVG(Current Year - Release Year)`  
- Insight: Both platforms have an average app age of 7 years.  
- Business Importance: Indicates market maturity and app lifecycle.  


## Slicer

To enable dynamic filtering, a slicer was implemented. The Category slicer was applied.

- **Field Used**: `CategoryTable[Category]`  
- **Why**: Allows filtering KPIs and charts by app category.  
- **Importance**: Helps in analyzing category-specific trends.  

---

## Recommendations

### Focus on High-Retention Categories

- Prioritize investment in categories like Tools, Action, and Music, which show higher retention rates.  
- Develop engagement strategies, such as loyalty rewards or personalized recommendations, to keep users active.  

### Optimize Monetization Strategies

- Apple App Store can increase user adoption by expanding freemium models with in-app purchases.  
- Google Play Store should refine ad-based monetization and introduce premium-tiered subscriptions for high-engagement apps.  

### Improve App Discoverability & Ratings

- Invest in App Store Optimization (ASO) using keywords, engaging app previews, and responding to user reviews.  
- Address negative feedback by enhancing UI/UX and providing regular feature updates.  

### Increase Retention through Personalization

- Implement AI-driven recommendations to encourage continued app usage.  
- Use push notifications strategically to retain users without overwhelming them.  

### Leverage Predictive Insights for Market Growth

- Expand investment in growing app categories like gaming and utilities based on forecasted trends.  
- Identify declining categories early to shift resources effectively.  



## Conclusion

The Advanced Business Insights Dashboard provides a powerful analytical tool for app developers and Google Play executives to drive data-backed decisions. By integrating predictive analytics, competitor benchmarking and key performance indicators, this dashboard enables more informed strategic planning.
Key takeaways from this analysis highlight the importance of retention strategies, revenue optimization, and user engagement to improve app performance. Future enhancements may include AI-driven sentiment analysis, real-time data tracking, and deeper user segmentation to refine decision-making further. Implementing these insights will position Google Play Store and Apple App Store for sustained growth and competitive advantage.
