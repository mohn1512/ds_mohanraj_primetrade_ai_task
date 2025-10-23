# Trading Behavior vs Market Sentiment Analysis

This project analyzes the relationship between historical trading behavior and market sentiment, using the Fear & Greed Index. The goal is to understand how sentiment correlates with trading activity and profitability, identify potential trading signals, and derive actionable strategy recommendations.

## Dataset Used

1.  **Historical Trader Data:** Contains detailed records of individual trades, including size, profit/loss (PnL), fees, and timestamps.
2.  **Fear & Greed Index:** Provides daily sentiment values and classifications (Extreme Fear, Fear, Neutral, Greed, Extreme Greed).

## Analysis Steps

The analysis was conducted in several stages, covering data loading and preprocessing, exploratory data analysis, correlation analysis, performance evaluation by sentiment regime, identification of hidden trends, and machine learning insights.

1.  **Data Loading & Preprocessing:**
    *   Loading the historical trading data and Fear & Greed Index data.
    *   Converting timestamp columns to datetime objects.
    *   Aggregating trading data to daily metrics (Total Volume, Total PnL, Trade Count, Total Fees).
    *   Merging the daily trading metrics with the Fear & Greed Index data based on date.

2.  **Market Sentiment Analysis:**
    *   Visualizing the distribution of sentiment values and classifications.
    *   Plotting the Fear & Greed Index trend over time.
    *   Summarizing key sentiment statistics (mean, median, std dev, min, max).

3.  **Trading Activity Analysis:**
    *   Visualizing daily trading volume, PnL, cumulative PnL, and trade count over time.

4.  **Sentiment vs Trading Behavior Correlation:**
    *   Analyzing the relationship between sentiment value and key trading metrics (Volume, PnL, Trade Count) using scatter plots and correlation coefficients.

5.  **Performance by Sentiment Regime:**
    *   Evaluating trading performance metrics (PnL distribution, Average PnL, Win Rate, Volatility) across different sentiment classifications.

6.  **Hidden Trends & Advanced Signals:**
    *   Creating custom indicators like daily return, sentiment moving averages (7-day and 21-day), and sentiment momentum.
    *   Visualizing these indicators to identify potential trading signals.

7.  **Strategy Recommendations:**
    *   Defining simple trading signals based on sentiment classification (BUY on Extreme Fear, SELL on Extreme Greed, HOLD otherwise).
    *   Analyzing the performance (Average PnL, Win Rate, Sharpe Ratio) of these signals.
    *   Investigating optimal position sizing strategies based on sentiment and trade characteristics.

8.  **Summary Report:**
    *   Generating a comprehensive executive summary of key performance metrics, correlation insights, sentiment regime performance, and actionable recommendations.

9.  **Machine Learning Feature Importance:**
    *   Building an XGBoost Regressor model to predict daily trading success (PnL above median).
    *   Analyzing feature importance to understand which factors (Sentiment, Volume, Trade Count, Fees) are most predictive of profitable days.

10. **Divergence & Alignment Analysis:**
    *   Analyzing how often actual trading performance aligns with expected performance based on sentiment regimes.
    *   Quantifying the divergence rate across different sentiment classifications to identify periods of higher unpredictability.

## Key Findings

*   **Weak Sentiment Correlation:** There is a weak negative correlation between market sentiment and trading activity (volume, trade count, fees), and a very weak negative correlation with PnL. This suggests that while there's a slight tendency for activity and PnL to decrease in greedier markets, the relationship is not strong.
*   **Performance Varies by Sentiment:** Trading performance metrics (Average PnL, Win Rate) differ across sentiment regimes. Extreme Fear and Extreme Greed periods show distinct performance characteristics.
*   **Extreme Greed is Highly Unpredictable:** The analysis revealed a high divergence rate, particularly in Extreme Greed periods, indicating that actual trading outcomes often do not align with simple sentiment-based expectations during these times.
*   **Trading Activity is a Stronger Predictor:** The machine learning model highlighted that trading activity metrics (Trade ID, Size USD, Fee) are significantly stronger predictors of daily trading success (above/below median PnL) than the sentiment value itself.
*   **Actionable Signals Exist:** Despite the weak overall correlation, specific sentiment regimes (like Extreme Fear) may offer better risk-adjusted return opportunities, suggesting that a contrarian approach or dynamic strategy based on sentiment could be beneficial.

## Actionable Recommendations

Based on the analysis, the following trading strategy recommendations are suggested:

1.  **Consider Increasing Size in Extreme Fear:** Periods of Extreme Fear may offer favorable conditions for larger position sizes due to potentially better risk-adjusted returns observed in the analysis.
2.  **Reduce Risk in Extreme Greed:** Extreme Greed periods show high volatility and unpredictability; reducing position sizes or exercising caution may be prudent.
3.  **Focus on Trade Quality:** The weak correlation between PnL and trade activity metrics suggests that focusing on the quality and selection of trades might be more important than simply increasing the number of trades.
4.  **Implement Dynamic Position Sizing:** Adjusting position sizes based on the current sentiment regime and its associated volatility could help optimize risk and reward.
5.  **Utilize Moving Averages and Momentum:** Sentiment moving averages (7-day, 21-day) and sentiment momentum can potentially be used as additional signals for entry/exit or confirmation of trend changes.
6.  **Monitor for Divergence:** Be aware that sentiment and performance frequently diverge. Do not rely solely on sentiment as a trading signal; incorporate other technical or fundamental analysis.

## Visualizations

All generated visualizations are saved to the `outputs/` folder:

*   `01_sentiment_analysis.png`
*   `02_trading_activity.png`
*   `03_sentiment_trading_correlation.png`
*   `04_performance_by_sentiment_regime.png`
*   `05_correlation_matrix.png`
*   `06_hidden_trends_signals.png`
*   `07_strategy_recommendations.png`
*   `08_summary_report.png`
*   `09_ml_feature_importance.png`
*   `10_divergence_alignment_analysis.png`

## Conclusion

This analysis demonstrates that while market sentiment, as measured by the Fear & Greed Index, has some relationship with trading behavior, it is not a standalone predictor of trading success. Trading activity metrics and a nuanced understanding of performance across different sentiment regimes, particularly recognizing periods of high divergence, are crucial for developing effective trading strategies.
