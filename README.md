# Books & Quotes Data Analysis

An end-to-end data science and web scraping project analyzing book information and quote sentiment.

## 📁 Repository Structure

```text
books_data-analysis/
├── data/
│   ├── books_data.csv       # Scraped books dataset (title, price, rating, availability, category)
│   └── quotes_data.csv      # Scraped quotes dataset with author & tags
├── notebooks/
│   ├── web_scraping.ipynb   # Web scraping pipeline for books & quotes
│   ├── eda.ipynb            # Exploratory Data Analysis & data cleaning
│   ├── visualization.ipynb  # Data visualizations and chart generation
│   └── sentiment_analysis.ipynb # Sentiment analysis on quotes
├── .gitignore
└── README.md
```

## 📊 Overview

1. **Web Scraping (`web_scraping.ipynb`)**: Scrapes book data (titles, prices, ratings, availability, categories) and quote details.
2. **Exploratory Data Analysis (`eda.ipynb`)**: Cleans raw data, handles missing values, and inspects data distributions.
3. **Data Visualization (`visualization.ipynb`)**: Generates visual insights regarding book pricing, rating distributions, and category trends.
4. **Sentiment Analysis (`sentiment_analysis.ipynb`)**: Analyzes text sentiment across collected quotes and categories.

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/shreyaa89722-lang/books_data-analysis.git
   cd books_data-analysis
   ```

2. Install dependencies:
   ```bash
   pip install pandas matplotlib seaborn nltk beautifulsoup4 requests
   ```

3. Explore the notebooks in the `notebooks/` directory!
