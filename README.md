# Book Data Analysis Project

A 4-part data analysis pipeline: scraping real book data from the web, exploring it, visualizing key findings, and analyzing sentiment in real text data — built to demonstrate the full data analyst workflow from raw data collection to actionable insight.

## Project Overview

This project follows four stages, each building on the last:

1. **Web Scraping** — collected structured book data directly from a live website
2. **Exploratory Data Analysis (EDA)** — investigated the data, tested assumptions, and caught data quality issues
3. **Data Visualization** — turned findings into clear, readable charts
4. **Sentiment Analysis** — analyzed real text data to classify emotional tone

## Tools Used

- **Python** — core language
- **Requests + BeautifulSoup** — web scraping
- **Pandas** — data cleaning and analysis
- **Matplotlib** — data visualization
- **NLTK (VADER)** — sentiment analysis

## Task 1: Web Scraping

Scraped 100 books from [books.toscrape.com](https://books.toscrape.com), a site built for scraping practice. For each book, collected:
- Title
- Price (converted from GBP to INR)
- Star rating (converted to numeric 1-5)
- Stock count
- Category

Data was cleaned and saved to `books_data.csv`.

## Task 2: Exploratory Data Analysis

Explored the scraped dataset by asking meaningful questions:
- How are prices distributed?
- Does price vary meaningfully by category?
- Is there a relationship between price, rating, and stock count?
- Are there any anomalies or data quality issues?

**Key finding:** Two category values ("Add a comment", "Default") looked like scraping errors but were verified — via direct inspection of the site's HTML — to be genuine placeholder categories on the source site itself. They were relabeled as "Uncategorized" rather than assumed to be bugs.

**Result:** No meaningful correlation found between price, rating, and stock count (all under 0.15) — consistent with the site's own disclosure that ratings and stock are randomly assigned.

## Task 3: Data Visualization

Built 5 visuals to communicate the EDA findings clearly:
- Price distribution (histogram) — revealed a bimodal pattern (two price clusters, not one smooth average)
- Average price by category — limited to categories with 5+ books, to avoid misleading small-sample averages
- Price vs. Rating (scatter plot) — visually confirmed no relationship
- Category distribution — showed a heavily imbalanced dataset
- Rating distribution — confirmed near-even spread across 1-5 stars

## Task 4: Sentiment Analysis

Since the scraped book listings had no review/opinion text, sentiment analysis was performed on a separate, real text dataset: 100 quotes scraped from [quotes.toscrape.com](https://quotes.toscrape.com).

- Used VADER (NLTK) to classify each quote as Positive, Negative, or Neutral
- Result: 48 Positive, 28 Negative, 24 Neutral
- Noted a real limitation: VADER occasionally misreads humor/sarcasm as literal negative sentiment
- Applied sample-size caution when ranking authors by sentiment, only trusting averages for authors with 3+ quotes

## Key Takeaways

- Real-world data is messy — this project intentionally documents genuine data quality issues found and how they were resolved, rather than presenting only clean results
- Small sample sizes can distort averages — a recurring theme across both the EDA and sentiment analysis stages
- Automated tools (scrapers, sentiment models) have real limitations that should be acknowledged, not hidden

## Project Structure

```
books-data-analysis-project/
├── README.md
├── data/
│   ├── books_data.csv
│   └── quotes_data.csv
├── notebooks/
│   ├── 01_web_scraping.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_visualization.ipynb
│   └── 04_sentiment_analysis.ipynb
└── requirements.txt
```
