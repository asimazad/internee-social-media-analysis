# Internee.pk Social Media Engagement Analysis

## 1. Project Overview

This project analyzes social media engagement data to identify trends and patterns that can support future content strategy decisions.

The analysis covers:

- Likes
- Comments
- Shares
- Views
- Engagement Rate
- Platform performance
- Content type
- Content category
- Day of week
- Hour of day
- Sentiment
- Media presence
- Engagement over time

---

## 2. Objective

The objective of this project is to measure social media engagement trends and identify patterns that can help optimize future content strategies.

The analysis focuses on social media engagement indicators such as:

- Likes
- Comments
- Shares
- Views
- Engagement Rate

---

## 3. Dataset

The available CSV dataset contains:

- 5,000 rows
- 20 original columns

Important columns include:

- `Post_ID`
- `Timestamp`
- `Platform`
- `Content_Type`
- `Category`
- `Likes`
- `Comments`
- `Shares`
- `Views`
- `Saves`
- `Follower_Count`
- `Engagement_Rate`
- `Hour_of_Day`
- `Day_of_Week`
- `Hashtag_Count`
- `Content_Length`
- `Sentiment`
- `Influencer_Tier`
- `Has_Media`
- `Is_Verified`

### Dataset Limitation

The dataset contains `Views` rather than `Reach`. Therefore, `Views` is used as the available visibility metric and is not presented as Reach.

The dataset is treated as a public/sample dataset and is **not** presented as Internee.pk's private internal analytics.

---

## 4. Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- Requests
- OpenPyXL

---

## 5. Project Structure

```text
internee-social-media-analysis/
│
├── data/
│   └── social_media_engagement_dataset.csv
│
├── notebooks/
│   └── social_media_analysis.ipynb
│
├── src/
│   ├── data_cleaning.py
│   ├── analysis.py
│   └── api/
│       ├── instagram_api.py
│       ├── facebook_api.py
│       └── linkedin_api.py
│
├── visualizations/
│
├── report/
│   ├── report.md
│   ├── platform_summary.csv
│   ├── content_summary.csv
│   ├── category_summary.csv
│   ├── day_summary.csv
│   ├── hour_summary.csv
│   ├── sentiment_summary.csv
│   ├── media_summary.csv
│   └── interaction_summary.csv
│
├── .gitignore
├── README.md
└── requirements.txt
```

---

## 6. Data Analysis Workflow

```text
Data Collection
      ↓
Data Inspection
      ↓
Data Cleaning
      ↓
Feature Creation
      ↓
Exploratory Data Analysis
      ↓
Visualization
      ↓
Findings
      ↓
Recommendations
```

---

## 7. Data Cleaning and Validation

The dataset was loaded using Pandas and inspected before analysis. The following checks were performed:

- Dataset shape
- Column names
- Missing values
- Duplicate rows
- Data types
- Platform distribution
- Content type distribution

The `Timestamp` column was converted into datetime format for time-based analysis:

```python
df["Timestamp"] = pd.to_datetime(df["Timestamp"])
```

The dataset was also checked for missing values and duplicate records.

---

## 8. Total Engagement Calculation

A new column called `Total_Engagement` was created:

```python
df["Total_Engagement"] = (
    df["Likes"] +
    df["Comments"] +
    df["Shares"]
)
```

The calculation represents the combined number of Likes, Comments, and Shares. This metric was used throughout the analysis to compare engagement performance.

---

## 9. Platform Analysis

The dataset was grouped by `Platform`. The following metrics were calculated:

- Number of Posts
- Average Likes
- Average Comments
- Average Shares
- Average Views
- Average Engagement
- Average Engagement Rate

A visualization was created to compare average engagement across platforms.

**Finding:** TikTok had the highest average engagement among the platforms represented in the available dataset. This is a dataset-level finding and should not be interpreted as verified Internee.pk private analytics.

---

## 10. Average Views by Platform

Average Views were compared across platforms using a bar chart. Since the dataset contains Views rather than Reach, Views were used as the available visibility metric.

---

## 11. Content Type Analysis

The dataset was grouped by `Content_Type`. The following metrics were calculated:

- Number of Posts
- Average Likes
- Average Comments
- Average Shares
- Average Views
- Average Engagement
- Average Engagement Rate

**Finding:** Duet had the highest average engagement among the available content types.

---

## 12. Category Analysis

The dataset was grouped by `Category`. The same set of metrics was calculated.

**Finding:** Food had the highest average engagement among the available categories.

---

## 13. Day-of-Week Analysis

The dataset was grouped by `Day_of_Week`, analyzing:

- Number of Posts
- Average Likes
- Average Comments
- Average Shares
- Average Engagement
- Average Views

**Finding:** Wednesday recorded the highest average engagement among the days analyzed.

---

## 14. Hour-of-Day Analysis

The dataset was grouped by `Hour_of_Day`, calculating average engagement and average views. A line chart was created to visualize engagement across hours.

**Finding:** 18:00 (6 PM) recorded the highest average engagement among the available hours. This result can be used as a timing pattern to test further rather than as a guaranteed best posting time.

---

## 15. Sentiment Analysis

The dataset was grouped by `Sentiment`, with the same metric set calculated.

**Finding:** Positive sentiment recorded the highest average engagement among the sentiment categories.

---

## 16. Media vs Non-Media Analysis

Posts with media were compared to posts without media.

| Media          | Average Engagement |
|----------------|--------------------|
| Without Media  | 8586.51            |
| With Media     | 8734.98            |

Difference: `8734.98 - 8586.51 = 148.47`

Media-containing posts had 148.47 higher average engagement in this dataset.

---

## 17. Engagement Over Time

The `Timestamp` column was converted into datetime format, and the data was grouped by date to calculate average engagement, average views, and number of posts. A line chart was created to visualize the engagement trend over time.

---

## 18. Likes, Comments, and Shares Analysis

Average values of Likes, Comments, and Shares were calculated separately, with a comparison chart created to understand the relative level of different interaction types.

---

## 19. Key Findings Summary

| Analysis     | Highest Average Engagement |
|--------------|-----------------------------|
| Platform     | TikTok                      |
| Content Type | Duet                        |
| Category     | Food                        |
| Day          | Wednesday                   |
| Hour         | 18:00                       |
| Sentiment    | Positive                    |

| Media Status  | Average Engagement |
|---------------|---------------------|
| Without Media | 8586.51             |
| With Media    | 8734.98             |

---

## 20. Recommendations

Based on the observed patterns:

- Test high-performing content formats more frequently while continuing to measure their performance.
- Test Wednesday and around 6 PM as potential publishing periods.
- Continue monitoring positive-sentiment content to determine whether the observed pattern remains consistent.
- Test media-based content further because posts containing media showed slightly higher average engagement.
- Compare different content categories before making long-term content strategy decisions.
- Monitor Likes, Comments, Shares, Views, and Engagement Rate together rather than relying on a single metric.
- Validate these patterns using actual authorized social media platform analytics before applying them specifically to Internee.pk.

---

## 21. API Integration

The project contains separate API modules for Instagram, Facebook, and LinkedIn:

- `src/api/instagram_api.py`
- `src/api/facebook_api.py`
- `src/api/linkedin_api.py`

The API modules are designed to use access tokens through environment variables. API credentials are not hard-coded into the source code.

### API Status

The API project structure has been prepared. Actual Instagram, Facebook, and LinkedIn API results have not been fabricated. Actual API data should only be added after authorized API access is available.

---

## 22. Limitations

**Dataset Limitation:** The available dataset is treated as a public/sample dataset and is not presented as Internee.pk's private internal analytics.

**Reach Limitation:** The dataset contains Views, not Reach. Therefore, Views are used as the available visibility metric.

**Platform Limitation:** The assignment focuses on Instagram, Facebook, and LinkedIn, while the available dataset also contains other platform data, including TikTok. Therefore, the TikTok result is reported only as a finding from the available dataset.

**API Limitation:** Actual API results require authorized access to the respective platforms. No fake API results have been used.

**Generalization Limitation:** The findings describe patterns in the available dataset and should be validated against actual Internee.pk analytics before being treated as official performance results.

---

## 23. Future Improvements

Future development can include:

- Connecting authorized Instagram API data
- Connecting authorized Facebook API data
- Connecting authorized LinkedIn API data
- Combining API data with the existing dataset
- Automating data collection
- Creating an interactive dashboard
- Adding automated reports
- Monitoring engagement trends continuously

---

## 24. Conclusion

This project demonstrates how Python-based data analysis can be used to examine social media engagement patterns. The analysis evaluates platform performance, content types, categories, posting days, posting hours, sentiment, media presence, Likes, Comments, Shares, Views, Engagement Rate, and engagement trends over time.

The results provide data-driven patterns that can be used to develop and test future content strategies. However, these findings should be validated with authorized Internee.pk platform analytics before being treated as official Internee.pk performance results.

---

## Author

- Asim Azad
- Internee.pk Social Media Engagement Analysis Project

- Built using: Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook, Requests
