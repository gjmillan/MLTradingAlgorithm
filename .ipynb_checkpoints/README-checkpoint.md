# Machine Learning Trading Bot

![Decorative image.](Images/14-challenge-image.png)


## Background

In this Challenge, you’ll assume the role of a financial advisor at one of the top five financial advisory firms in the world. Your firm constantly competes with the other major firms to manage and automatically trade assets in a highly dynamic environment. In recent years, your firm has heavily profited by using computer algorithms that can buy and sell faster than human traders.

The speed of these transactions gave your firm a competitive advantage early on. But, people still need to specifically program these systems, which limits their ability to adapt to new data. You’re thus planning to improve the existing algorithmic trading systems and maintain the firm’s competitive advantage in the market. To do so, you’ll enhance the existing trading signals with machine learning algorithms that can adapt to new data.

## Conclusion
This algorithm, through Machine Learning, has the ability to analyzed investment data in order to learn and adapt to new information and evolving markets. As you will see in the Jupyter notebook, you will find the strategy to automate the model's trade decisions and view its performance overtime. Furthermore, you can change the parameters in the notebook in order to view it's strategies and executions based on different timelines.

In the graph below, you can find an overall performance of the algorithm with a timeline from 2015 through 2021 from the data imported through a CSV file which contains the trading data of the timeline. The graph details that the algorithm performance was the same as the actual returns of the portfolio up until the middle of 2017. From mid 2017 until mid 2018, the algorithm underperformed the portfolio actual returns. Starting mid 2018 through 2021, the algorithm outperformed the portfolio actual returns.

Overall, we can see that the algorithm performanced was tied to the portfolio performance. Whenever the market performed positively over a long stretch of time, the algorithm performed the same or at times better than the market. On the other hand, the algorithm underperformed the market during negative market returns. With this analysis, we can conclude that the algorithm is very volatile, and decisions on when and how to execute should be throughly considered and understand its risks.

![Decorative image.](Images/Returns_Algo.png)


## Training Window Tuning
In the below three analysis, you will find the impact to the algorithm when there was a change or tuning to the DateOffset or the SMA timeline, and at what timeline the algorithm performed best.


## DateOffset Increased to 6 Months From 3 Months
In the original analysis the DateOffset is set at 3 months, so for further analysis and understanding of the algorithm, the timeline was expanded to 6 months. The result of the algorithm performance can be found in the graph below.

The impact was a lower performance for the algorithm. As seen in the graph below, the algorithm underperformed the portfolio actual returns for a longer timeline, and overperformed for shorter timeline. This led for the algorithm to have a lower timeline and ability to learn from the data and have better returns for a long period of time.

![Decorative image.](Images/6Month_Analysis.png)

## SMA Doubled for both Short-Term & Long-Term
In the original analysis the SMA for short-term was set at 4 and long-term SMA at 100. For this next analysis I decided to double both the short-term SMA and long-term SMA to 8 and 200 respectively. The result of the algorithm performance in comparison with portfolio actual returns can be found in the graph below.

By doubling the SMA we found that the algorithm was never able to outperformed the portfolio actual returns. This was a concequence of the algorithm  viewing bigger chunks of the data rather than smaller chunks in order to learn from the data and change its strategy to better performed. This notes that the algorithm will better performed with a lower SMA.

![Decorative image.](Images/SMA_Increased.png)

## Decreased in SMA and DateOffset for Best Algo Performance
By decreasing both the SMA and DateOffset, the best perfoming algorithm is the result of an adjusted SMA and DateOffset.

As seen in the graph below, with these parameters the algorithm is able to outperformed the portfolio actual returns for an extended period of time. This was a capability when an algorithm is able to read the data accurately and therefore be able to adjust quicker in order to outperformed the portfolio actual returns for the remaining timeline of the dataset.

![Decorative image.](Images/SMA_DateOffset_Decreased.png)

## What You're Creating

You’ll combine your new algorithmic trading skills with your existing skills in financial Python programming and machine learning to create an algorithmic trading bot that learns and adapts to new data and evolving markets.

In a Jupyter notebook, you’ll do the following:

* Implement an algorithmic trading strategy that uses machine learning to automate the trade decisions.

* Adjust the input parameters to optimize the trading algorithm.

* Train a new machine learning model and compare its performance to that of a baseline model.

As part of your GitHub repository’s `README.md` file, you will also create a report that compares the performance of the machine learning models based on the trading predictions that each makes and the resulting cumulative strategy returns.

## Files

Download the following files to help you get started:

[Unit 14 homework files](Starter_Code/Starter_Code.zip)

> **Note:** The provided CSV file contains OHLCV data for an MSCI&ndash;based emerging markets ETF that [iShares](https://www.ishares.com/us/products/268704/ishares-currency-hedged-msci-emerging-markets) issued. Investments in emerging markets make up an important aspect of a well-diversified investment portfolio. This is because the included equities have potentially higher long-term returns, even though they carry more risk.

## Instructions

Use the starter code file to complete the steps that the instructions outline. The steps for this Challenge are divided into the following sections:

* Establish a Baseline Performance

* Tune the Baseline Trading Algorithm

* Evaluate a New Machine Learning Classifier

* Create an Evaluation Report

### Establish a Baseline Performance

In this section, you’ll run the provided starter code to establish a baseline performance for the trading algorithm. To do so, complete the following steps.

Open the Jupyter notebook. Restart the kernel, run the provided cells that correspond with the first three steps, and then proceed to step four.

1. Import the OHLCV dataset into a Pandas DataFrame.

2. Generate trading signals using short- and long-window SMA values.

3. Split the data into training and testing datasets.

4. Use the `SVC` classifier model from SKLearn's support vector machine (SVM) learning method to fit the training data and make predictions based on the testing data. Review the predictions.

5. Review the classification report associated with the `SVC` model predictions.

6. Create a predictions DataFrame that contains columns for “Predicted” values, “Actual Returns”, and “Strategy Returns”.

7. Create a cumulative return plot that shows the actual returns vs. the strategy returns. Save a PNG image of this plot. This will serve as a baseline against which to compare the effects of tuning the trading algorithm.

8. Write your conclusions about the performance of the baseline trading algorithm in the `README.md` file that’s associated with your GitHub repository. Support your findings by using the PNG image that you saved in the previous step.

### Tune the Baseline Trading Algorithm

In this section, you’ll tune, or adjust, the model’s input features to find the parameters that result in the best trading outcomes. (You’ll choose the best by comparing the cumulative products of the strategy returns.) To do so, complete the following steps:

1. Tune the training algorithm by adjusting the size of the training dataset. To do so, slice your data into different periods. Rerun the notebook with the updated parameters, and record the results in your `README.md` file. Answer the following question: What impact resulted from increasing or decreasing the training window?

    > **Hint** To adjust the size of the training dataset, you can use a different `DateOffset` value&mdash;for example, six months. Be aware that changing the size of the training dataset also affects the size of the testing dataset.

2. Tune the trading algorithm by adjusting the SMA input features. Adjust one or both of the windows for the algorithm. Rerun the notebook with the updated parameters, and record the results in your `README.md` file. Answer the following question: What impact resulted from increasing or decreasing either or both of the SMA windows?

3. Choose the set of parameters that best improved the trading algorithm returns. Save a PNG image of the cumulative product of the actual returns vs. the strategy returns, and document your conclusion in your `README.md` file.

### Evaluate a New Machine Learning Classifier

In this section, you’ll use the original parameters that the starter code provided. But, you’ll apply them to the performance of a second machine learning model. To do so, complete the following steps:

1. Import a new classifier, such as `AdaBoost`, `DecisionTreeClassifier`, or `LogisticRegression`. (For the full list of classifiers, refer to the [Supervised learning page](https://scikit-learn.org/stable/supervised_learning.html) in the scikit-learn documentation.)

2. Using the original training data as the baseline model, fit another model with the new classifier.

3. Backtest the new model to evaluate its performance. Save a PNG image of the cumulative product of the actual returns vs. the strategy returns for this updated trading algorithm, and write your conclusions in your `README.md` file. Answer the following questions: Did this new model perform better or worse than the provided baseline model? Did this new model perform better or worse than your tuned trading algorithm?

### Create an Evaluation Report

In the previous sections, you updated your `README.md` file with your conclusions. To accomplish this section, you need to add a summary evaluation report at the end of the `README.md` file. For this report, express your final conclusions and analysis. Support your findings by using the PNG images that you created.

---

## Submission

* Use the started code provided to create the machine learning trading bot and host the notebook and the required files.

* Include a `README.md` file with your conclusions as requested.

* Submit the link to your GitHub project to Bootcamp Spot.

---

© 2022 edX Boot Camps LLC. Confidential and Proprietary. All Rights Reserved.
