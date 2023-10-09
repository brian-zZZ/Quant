# Deep Learning-based Quantitative Investment Framework
Algorithm Implementation Overview:
1. Sentiment Analysis: Comprehensive consideration of both the title and content information of news. Pegasus is used to summarize the news content, and Albert is used for sentiment analysis and representation of the news title+content summary text.
2. Feature Construction: Construct technical factors from historical stock trading data to obtain fundamental features. Concatenate fundamental features with news sentiment features to obtain global features.
3. Model Construction: Utilize sequence models LSTM and Transformer.
4. Backtesting and Evaluation: Trading strategies involving profit-taking, stop-loss, and rotation strategies are applied. Backtesting is performed on the test dataset.

## Workflow
* 1-news_collecting: Automated news collection script. Data source: Eastmoney (www.eastmoney.com).
* 2-news_summarizing: Summarization of news content. Leveraging the pre-trained `Pegasus` model on a large-scale Chinese dataset.
* 3-sentiment_finetuning: Fine-tuning of the sentiment analysis model. Utilizing the pre-trained `Albert` model on Chinese sentiment data and further fine-tuning on the `ChnSentiCrop` dataset.
* 4-sentiment_analyzing: Sentiment analysis and representation. Utilizing the previously fine-tuned `Albert` model to perform sentiment analysis on daily news and obtain news representation.
* 5-investment_modeling: Investment modeling. Predicting daily stock price movements, defining trading strategies, and providing trading decisions.

## Datasets
* Historical Trading Data: Utilizing trading data from the Chinese stock market, including Shenzhen Stock Exchange and Shanghai Stock Exchange, comprising data for over 4000 stocks. Trading date range: 2020/01/01 - 2022/12/30.
* News Data: Collecting daily news (including titles and content) for over 4000 stocks.
* Data Splitting: Train set: 2020/01/01 - 2022/06/30; Test set: 2022/07/01 - 2022/12/30.

## Info
Author: Weihong Zhang, College of AI, UCAS.

## Acknowledgement
The SOFTWARE will be used for teaching or not-for-profit research purposes only. Permission is required for any commercial use of the Software.
