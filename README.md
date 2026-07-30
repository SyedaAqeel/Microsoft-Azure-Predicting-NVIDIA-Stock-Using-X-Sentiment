# From Tweets to Trends: Predicting Stock Prices Using X Sentiment

This project builds a fully automated, self-retraining pipeline that ingests tweets and stock data, engineers sentiment and engagement features, trains a volume-prediction model, and surfaces daily results through a Power BI dashboard — all orchestrated on Azure with a daily feedback loop.


## Course

* DS598 Big Data Engineering - Boston University 


## Team:

* Syeda Aqeel
* Yuchen Li
* Hsiang Yu Huang


## Overview

Social sentiment on X moves fast, and financial markets increasingly respond to it in real time. Rather than trying to predict the notoriously volatile stock price, this project predicts NVIDIA's next-day trading volume, a target that correlates more reliably with public sentiment and engagement metrics. Potential use cases include algorithmic trading signals, market risk monitoring, investor relations, and influencer/marketing analysis. See the full report for a detailed discussion of business applications.


## Architecture

<p align="center">
  <img src="Workflow.png">
</p>


## Data Sources

| Data | Source | 
|---|---|
| **X/Twitter** | RapidAPI Twitter V2 | 
| **Stock Data** | Yahoo Finance |


## Key Findings

- Trading volume showed a much stronger, more interpretable correlation with sentiment/engagement than price did — validating the choice of volume as the prediction target.
- The DeepSeek launch triggered a clear sentiment-driven volume spike, with recovery as sentiment shifted — evidence that sentiment can lead market activity.
- Tweets from blue-verified accounts drove disproportionately higher engagement, suggesting credibility-weighted sentiment could improve future models.
- "Favorites" was the dominant engagement signal (vs. retweets/replies), and likely the cleaner proxy for approval/sentiment resonance.
- NVDA tweets frequently co-mentioned other tech tickers (TSLA, AMD, MSFT), hinting at cross-stock sentiment spillover.


## Challenges & Optimizations

- **Data skew:** engagement metrics were heavily right-skewed; addressed with log transforms and scaling.
- **SQL pool cost:** dedicated Synapse SQL pools bill for idle compute; solved with an automated resume/pause orchestration around refresh windows.
- **Opaque API pagination:** RapidAPI's cursor never signals exhaustion; solved with a custom `Until`-loop that inspects the response body to detect completion.
- **Retraining threshold tuning:** a 1% relative error threshold balanced responsiveness against overfitting/excessive retraining.


## Future Work

- Incorporate weekend tweets to improve Monday volume predictions.
- Use total NVDA tweet volume (if accessible) as an additional feature.
- Add anomaly detection for unusual tweet or trading patterns.
- Extend to multiple tickers for broader market coverage.
- Explore more advanced NLP models for deeper sentiment/context understanding.


## References

1. Patel & Bhesaniya, "Analysis and Prediction of Stock Market Using Twitter Sentiment and DNN," ResearchGate, 2019.
2. Tripathy et al., "Stock Market Prediction Using Twitter Sentiment Analysis," ResearchGate, 2021.
3. Ranco et al., "The Effects of Twitter Sentiment on Stock Price Returns," ResearchGate, 2015.
4. Salas-Zárate et al., "Stock Market Forecasting Using Sentiment Analysis: A Review," *Electronics*, 2022.
5. Prabhu, "Machine Learning for Stock Trading: Unsupervised Learning Techniques," Analytics Vidhya, 2019.
6. Bollen et al., "Twitter Mood Predicts the Stock Market," *Procedia Computer Science*, 2010.
7. Atef, "Stock Market Prediction Using Sentiment Analysis of Twitter," GitHub.
8. Microsoft Learn, "Pause and Resume Dedicated SQL Pools Using Pipelines in Azure Synapse Analytics."

