# fintech14_algo_trading

This is the homework submission for week 14 of the fintech bootcamp. In this exercise, we are comparing the performances of various algo-trading strategies and the impact of tuning certain parameters. All output plots are stored in the Plots folder.

The trading signals based on daily returns actually under-perform the actual returns significantly. Hence, building a ML model for outputting such signals is unlikely to yield great results.

Here are the findings for tuning different parameters:

Changing Training Window - Comparing svm_baseline, svm_12_months & svm_24_months, the algorithm performance actually diminishes as we increase the training window. This is likely due to increase in overfitting, and the model trained using only 3 months of data actually performs better in the selected testing period.

Changing SMA Window - Comparing svm_baseline, svm_2_50, svm_2_100, svm_20_100, svm_50_200, the baseline algorithm (short window of 4, long window of 100) still had the best performance in terms of outperforming actual returns. Given that the true signals are based on daily returns, increasing either window of the SMA would lower the accuracy of the SVM model on predicting the signals. Having a longer SMA window also by default shrinks the training set, since more days are factored into the average. Hence, it turns out that 4 and 100 is the optimal combination among the ones tested.

Logistic Regression - Using logistic regression instead of SVM did not outperform SVM (comparing svm_baseline & lr_baseline).

In conclusion, the SVM baseline performance (3 month training period, 4 & 100 SMA windows) was the most optimal.