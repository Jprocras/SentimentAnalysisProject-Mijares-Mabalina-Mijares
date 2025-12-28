# Sentiment Analysis Project: BLACKPINK Twitter Analysis

## Project Overview

This repository contains a sentiment analysis project that examines public opinion regarding BLACKPINK and its members through Twitter data during a specific time period (October 28-30, 2022). The analysis coincides with two significant events:
1. BLACKPINK's Houston concert
2. The Itaewon tragedy in South Korea

**Authors:** Mijares, Mabalina, Compay

## File Structure

- **Project_Sentiment_Analysis#(Mijares,Compay,Mabalina).Rmd** - Main R Markdown file containing the complete analysis
- **Project_Sentiment_Analysis--Mijares,Compay,Mabalina-.pdf** - PDF output of the analysis report
- **tweetsDF.csv** - Dataset containing Twitter data (14.7MB) with tweets related to BLACKPINK

## Use Case and Objectives

The project aims to:

1. **Understand Event Impact**: Analyze how external events (the Itaewon tragedy and concert continuation) affected social media activity and sentiment
2. **Provide Management Insights**: Deliver actionable insights for BLACKPINK's management team regarding public sentiment and engagement
3. **Crisis Management Strategy**: Inform public relations strategies during crises by identifying key trends and sentiments

## Technical Components

### Required R Libraries

The analysis uses the following R packages:

- **tidyverse**: Data manipulation and transformation
- **lubridate**: Date and time handling
- **ggplot2**: Data visualization
- **tidytext**: Text mining and analysis
- **sentimentr**: Sentiment analysis calculations

### Data Structure

The dataset (`tweetsDF.csv`) contains Twitter data with the following key columns:
- **created**: Timestamp of when the tweet was posted
- **text**: The actual tweet content
- Additional metadata about the tweets

## Analysis Workflow

### 1. Data Loading and Inspection

The analysis begins by:
- Loading the CSV dataset
- Inspecting the data structure using `str()`, `summary()`, and `head()`
- Verifying data integrity and understanding the dataset composition

### 2. Data Cleaning

Comprehensive data cleaning steps include:

- **Duplicate Removal**: Eliminating duplicate tweets using `distinct()`
- **Missing Value Handling**: Removing rows with missing data using `drop_na()`
- **Column Standardization**: Renaming 'created' to 'datetime' for consistency
- **Date-Time Conversion**: Converting timestamps to proper POSIXct format using `ymd_hms()`
- **Text Preprocessing**: Removing:
  - URLs (http/https links)
  - Hashtags (#)
  - Mentions (@)
  - Special characters
- **Keyword Filtering**: Filtering tweets containing: "Blackpink", "Rose", "Lisa", "Jennie", "Jisoo", or "concert"

### 3. Trend Analysis

The trend analysis focuses on the specific date range (October 28-30, 2022) and includes:

- **Temporal Filtering**: Restricting data to the three-day window
- **Daily Aggregation**: Counting tweets per day
- **Complete Date Coverage**: Ensuring all dates in the range are represented (even with zero counts)
- **Visualization**: Creating a line graph showing tweet volume over time

**Key Finding**: The analysis reveals:
- Gradual increase in mentions from October 28 to 29
- Significant spike on October 30
- The spike correlates with discussions about the Itaewon tragedy and BLACKPINK's concert continuation
- Public sentiment became divided between criticism and support
- Demonstrates social media's amplification effect for high-profile events

### 4. Sentiment Analysis

The sentiment analysis component:

- **Sentiment Scoring**: Using the `sentimentr` package to calculate average sentiment scores for each tweet
- **Categorization**: Classifying tweets into three categories:
  - **Positive**: sentiment > 0
  - **Negative**: sentiment < 0
  - **Neutral**: sentiment = 0
- **Visualization**: Creating a bar chart showing the distribution of sentiment categories with color coding (green for positive, red for negative, gray for neutral)

**Key Finding**: The sentiment distribution reveals:
- **Negative sentiments were most prevalent** during this period
- Criticism centered on BLACKPINK continuing their concert despite the tragedy
- Some negative tweets attributed to online trolls amplifying backlash
- Positive sentiments reflected fan support and prayers for tragedy victims
- Neutral sentiment was least represented, indicating strong polarization

## Key Insights and Conclusions

### Social Media Dynamics
- High-profile events create significant spikes in social media activity
- Controversies amplify discourse and increase engagement
- Social media acts as an amplifier for both support and criticism

### Public Sentiment
- The Itaewon tragedy created a divided public response
- Negative sentiment dominated, driven by perceived insensitivity
- Positive sentiment existed but was overshadowed by criticism
- Low neutral sentiment indicates emotional polarization

### Crisis Management Implications
- External tragedies significantly impact celebrity and brand perception
- Real-time sentiment monitoring is crucial during crisis periods
- Public relations strategies must account for emotional polarization
- Online trolls can amplify negative sentiment beyond organic levels

## Methodology Strengths

1. **Comprehensive Data Cleaning**: Rigorous preprocessing ensures data quality
2. **Focused Temporal Analysis**: Specific date range targets the event window
3. **Multi-Faceted Analysis**: Combines trend analysis with sentiment analysis
4. **Visual Communication**: Clear visualizations make insights accessible
5. **Contextual Interpretation**: Links quantitative findings to real-world events

## How to Reproduce This Analysis

1. **Install Required Packages**:
   ```r
   install.packages(c("tidyverse", "lubridate", "ggplot2", "tidytext", "sentimentr"))
   ```

2. **Load the R Markdown File**:
   Open `Project_Sentiment_Analysis#(Mijares,Compay,Mabalina).Rmd` in RStudio

3. **Update File Paths**:
   Modify the data loading path to match your local environment:
   ```r
   data <- read.csv("your/path/to/tweetsDF.csv")
   ```

4. **Knit the Document**:
   Click "Knit" in RStudio or run:
   ```r
   rmarkdown::render("Project_Sentiment_Analysis#(Mijares,Compay,Mabalina).Rmd")
   ```

## Potential Extensions

Future enhancements could include:
- Topic modeling to identify key discussion themes
- Network analysis of tweet interactions (retweets, replies)
- Comparison with other K-pop groups during similar events
- Geographic analysis of sentiment distribution
- Temporal sentiment evolution at hourly granularity
- Influencer identification and impact analysis

## Data Privacy and Ethics

This analysis uses publicly available Twitter data. Users should be aware of:
- Twitter's Terms of Service and data usage policies
- Privacy considerations when analyzing social media data
- Ethical implications of sentiment analysis on public figures
- The limitation that social media sentiment may not represent broader public opinion

## Contact

For questions or collaboration opportunities, please contact the project authors:
- Mijares
- Mabalina  
- Compay

---

*This project demonstrates practical applications of data science techniques in social media analysis, crisis communication, and public sentiment monitoring.*
