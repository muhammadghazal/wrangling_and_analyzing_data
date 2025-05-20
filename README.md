# WeRateDogs Twitter Data Analysis & Visualization

This project involves extensive data wrangling, analysis, and visualization of Twitter data from the WeRateDogs page. The goal is to extract actionable insights on tweet engagement, dog ratings, and classification stages by cleaning multiple datasets and generating visual reports.

---

## Data Sources

- **Twitter Archive:** `twitter_archive_enhanced.csv`  
- **Image Predictions:** `image_predictions.tsv`  
- **API Data:** `tweet_json.txt` (collected via the Twitter API)

---

## Objectives

1. **Interaction Analysis:**  
   - **Insight:** Examine the relation between `retweet_count` and `favorite_count`.  
   - **Finding:** A strong positive correlation (r ≈ 0.93) indicates that as retweets increase, likes follow closely.

2. **Dog Rating Distribution:**  
   - **Insight:** Evaluate the distribution of dog ratings, compute measures of central tendency, and understand skewness.  
   - **Finding:** The histogram is left-skewed with a median above the mean (≈10.53) and a maximum rating that often exceeds the conventional 10, reflecting passionate fan ratings.

3. **Dog Stage Frequency:**  
   - **Insight:** Identify which dog classification stage (e.g., doggo, puppo, pupper, floofer) is most common.  
   - **Finding:** The “pupper” stage is the most prevalent among tweet annotations.

---

## Data Wrangling & Cleaning

A rigorous cleaning process was applied to address quality and tidiness issues:
- **Quality Issues Fixed:**
  - Removed non-original tweets (replies and retweets).
  - Eliminated duplicate URLs in the `expanded_urls` column.
  - Corrected data types for IDs, timestamps, and rating fields.
  - Standardized missing values (e.g., replacing string `"None"` with proper nulls) and corrected inconsistent dog names.
  - Resolved out-of-range rating values in both numerator and denominator fields.

- **Tidiness Improvements:**
  - Merged related columns, e.g., grouping dog stage columns (doggo, puppo, pupper, floofer) into a unified `dog_stage` field.
  - Reshaped the image predictions table to separate observational units.

Final cleaned datasets are saved as:
- `twitter_archive_master.csv`
- `image_predictions_master.csv`

---

## Tools & Technologies

- **Programming Language:** Python 3.x  
- **Libraries:** pandas, numpy, tweepy, requests, re, json, matplotlib, seaborn, scipy, warnings  
- **Environment:** Jupyter Notebook for exploratory data analysis and visualization

---

## Usage

1. Install the required libraries:
   ```bash
   pip install pandas numpy tweepy requests matplotlib seaborn scipy
   ```
2. Place the data files in the project directory.
3. Open and run the Jupyter Notebook to view the complete data cleaning, analysis, and visualization workflow.
