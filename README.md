# From Tweets to Trends: Predicting Stock Prices Using X Sentiment

This project builds a fully automated, self-retraining pipeline that ingests tweets and stock data, engineers sentiment and engagement features, trains a volume-prediction model, and surfaces daily results through a Power BI dashboard — all orchestrated on Azure with a daily feedback loop.


## Course

* DS598 Big Data Engineering - Boston University 


## Team:

* Syeda Aqeel
* Yuchen Li
* Hsiang Yu Huang


## Overview

Social sentiment on X moves fast, and financial markets increasingly respond to it in real time. Rather than trying to predict the notoriously volatile stock price, this project predicts NVIDIA's next-day trading volume, a target that correlates more reliably with public sentiment and engagement metrics. Potential use cases include algorithmic trading signals, market risk monitoring, investor relations, and influencer/marketing analysis.


## Architecture

<p align="center">
  <img src="Workflow.png">
</p>


## Dataset

| Data | Source | 
|---|---|
| **X/Twitter** | RapidAPI Twitter V2 | 
| **Stock Data** | Yahoo Finance |


## References

1. Patel & Bhesaniya, "Analysis and Prediction of Stock Market Using Twitter Sentiment and DNN," ResearchGate, 2019.
2. Tripathy et al., "Stock Market Prediction Using Twitter Sentiment Analysis," ResearchGate, 2021.
3. Ranco et al., "The Effects of Twitter Sentiment on Stock Price Returns," ResearchGate, 2015.
4. Salas-Zárate et al., "Stock Market Forecasting Using Sentiment Analysis: A Review," *Electronics*, 2022.
5. Prabhu, "Machine Learning for Stock Trading: Unsupervised Learning Techniques," Analytics Vidhya, 2019.
6. Bollen et al., "Twitter Mood Predicts the Stock Market," *Procedia Computer Science*, 2010.
7. Atef, "Stock Market Prediction Using Sentiment Analysis of Twitter," GitHub.
8. Microsoft Learn, "Pause and Resume Dedicated SQL Pools Using Pipelines in Azure Synapse Analytics."

