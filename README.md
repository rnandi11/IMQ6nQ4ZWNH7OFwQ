# Apziva Project 2- Term Deposit Marketing

## Background:

A fintech startup in the European banking market are interested in developing a robust machine learning system that leverages information coming from call center data. They are looking for ways to improve the success rate for calls made to customers for any product that their clients offer. Towards this goal they are working on designing an ever evolving machine learning product that offers high success outcomes while offering interpretability for their clients to make informed decisions.

## Data Description:

The data comes from direct marketing efforts of a European banking institution. The marketing campaign involves making a phone call to a customer, often multiple times to ensure a product subscription, in this case a term deposit. <br>

Attributes:<br>
age : age of customer (numeric)<br>
job : type of job (categorical)<br>
marital : marital status (categorical)<br>
education (categorical)<br>
default: has credit in default? (binary)<br>
balance: average yearly balance, in euros (numeric)<br>
housing: has a housing loan? (binary)<br>
loan: has personal loan? (binary)<br>
contact: contact communication type (categorical)<br>
day: last contact day of the month (numeric)<br>
month: last contact month of year (categorical)<br>
duration: last contact duration, in seconds (numeric)<br>
campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)<br>
Output (desired target):<br>
y - has the client subscribed to a term deposit? (binary)<br>

## Goal(s):
Predict if the customer will subscribe (yes/no) to a term deposit (variable y). We are also interested in finding customers who are more likely to buy the investment product. Determine the segment(s) of customers our client should prioritize.

## Solution(s):
This project is divided into three parts: <br>
1. The first part contains dataset where call-related columns are dropped. The goal is to predict successful subscribers from customer background information. This solution is provided in the file `Apziva_2_restricteddata.ipnyb`. <br>
2. The second part uses the entire dataset to build a classification model with best prediction accuracy on the test data. This solution is provided in the file `Apziva_2_alldata.ipnyb`. <br>
3. The third part uses data for subscribers only, `y=1`. This data is used to segment customers that would help clients focus on certain customer groups. <br>

# Conclusion: 
We find `LightGBM classifier` to be the best performing model on the given dataset. The trained model (on the restricted training data) is used to make predictions on the entire dataset. We find that the model prediction can `reduce call duration drastically by 88%`, at the cost of `loosing 37% of the subscribers`. With the call data incorporated in the model, the best model gives `91.2% accuracy`. Since we are trying to mazimize the number of subscribers, the `recall` should be maximized. We find a `recall` value of `72%`. Finally, we implement the `k-means clustering` and `PCA` analysis to segment customer groups, and find that customers are segregated based on the `average yearly balance`, followed by `call duration`. Thus, to maximize successful calls to customers that subscribe, the clients should focus on high balance customers and increase their call duration for these specific customers.




