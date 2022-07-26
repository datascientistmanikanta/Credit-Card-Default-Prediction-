
# Credit Card Default Prediction

This project presents and discusses data-driven predictive models for predicting the defaulters among the credit card users. Data used include details like limit balance, age, sex, amount of bill statement, repayment status and amount of previous payment. The paper discusses which variables are the strongest predictors of default, and to make predictions on which customers are likely to default


## Problem Statement 

In this project my aim was to predict the case of customers default payments in Taiwan. From the perspective of risk management, the result of predictive accuracy of the estimated probability of default will be more valuable than the binary result of classification - credible or not credible clients. We can use the K-S chart to evaluate which customers will default on their credit card payments.

## Dataset
[Dataset](https://docs.google.com/spreadsheets/d/1J0Ja4eSrXtkZtjLt2evDqiJJnc1k2T-Z/edit?usp=sharing&ouid=108383443908656099857&rtpof=true&sd=true)

• X1: Amount of the given credit (NT dollar): it includes both the individual consumer credit and his/her family (supplementary) credit. 

• X2: Gender (1 = male; 2 = female). 
• X3: Education (1 = graduate school; 2 = university; 3 = high school; 4 = others). 

• X4: Marital status (1 = married; 2 = single; 3 = others). 

• X5: Age (year). 

• X6 - X11: History of past payment. We tracked the past monthly payment records (from April to September, 2005) as follows: X6 = the repayment status in September, 2005; X7 = the repayment status in August, 2005; . .

• X 11= the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; . . .; 8 = payment delay for eight months; 9 = payment delay for nine months and above. 

• X12-X17: Amount of bill statement (NT dollar). X12 = amount of bill statement in September, 2005; X13 = amount of bill statement in August, 2005; . . .; X17 = amount of bill statement in April, 2005.

• X18-X23: Amount of previous payment (NT dollar). X18 = amount paid in September, 2005; X19 = amount paid in August, 2005; . . .;X23 = amount paid in April, 2005. 

## Algorithm Used
1.	Logistic Regression:
Logistic Regression is actually a classification algorithm that was given the name regression due to the fact that the mathematical formulation is very similar to linear regression.
The function used in Logistic Regression is sigmoid function or the logistic function given by:
		f(x)= 1/1+e ^(-x)
 

The optimization algorithm used is: Maximum Log Likelihood. We mostly take log likelihood in Logistic:
 

2.	Random Forest Classifier:
Random Forest is a bagging type of Decision Tree Algorithm that creates a number of decision trees from a randomly selected subset of the training set, collects the labels from these subsets and then averages the final prediction depending on the most number of times a label has been predicted out of all.
 



3.	XGBoost-
To understand XGBoost we have to know gradient boosting beforehand. 

Gradient Boosting- 
Gradient boosted trees consider the special case where the simple model is a decision tree
 
In this case, there are going to be 2 kinds of parameters P: the weights at each leaf, w, and the number of leaves T in each tree (so that in the above example, T=3 and w=[2, 0.1, -1]).
When building a decision tree, a challenge is to decide how to split a current leaf. For instance, in the above image, how could I add another layer to the (age > 15) leaf? A ‘greedy’ way to do this is to consider every possible split on the remaining features (so, gender and occupation), and calculate the new loss for each split; you could then pick the tree which most reduces your loss.

XGBoost is one of the fastest implementations of gradient boosting. trees. It does this by tackling one of the major inefficiencies of gradient boosted trees: considering the potential loss for all possible splits to create a new branch (especially if you consider the case where there are thousands of features, and therefore thousands of possible splits). XGBoost tackles this inefficiency by looking at the distribution of features across all data points in a leaf and using this information to reduce the search space of possible feature splits.

### SMOTE Oversampling -
In the initial model fitting, we start by using all models’ default parameters. To compensate for the rare classes in the imbalance dataset, we use SMOTE(Synthetic Minority Over-Sampling Technique) method to over sample the minority class and ensure the sampling is not biased. What this technique does under the hood is simply duplicating examples from the minority class in the training dataset prior to fitting a mode. After SMOTE sampling, the dataset has equal size of 0s and 1s. 

In order to verify if SMOTE improves models’ performance, all 3 models are trained with SMOTE and without SMOTE. Below table shows the ROC_ AUC scores on training data improved significantly with all models after over sampling with SMOTE. This proves SMOTE is an effective method in sampling imbalanced dataset.


### Comparision within the 3 models . 
Logistic Regression has the highest recall but also the lowest precision. Random Forest outperforms Logistic Regression and XG Boost if measured on their F1 scores, which is the balance between precision and recall. XG Boost has a decent performance but it takes the most time to tune the model.

## Conclusion
Based on the exploratory data analysis, we discover that human characteristics are not the most important predictors of default, the payment status of the most 2 months and credit limit 

From the modeling, we are able to classify default risk with accessible customer data and find a decent model. Using a Logistic Regression classifier, we can predict with 73% accuracy, whether a customer is likely to default next month. Using a Random Forest classifier, we can predict with 92% accuracy, whether a customer is likely to default next month. Using a XG BOOST classifier, we can predict with 88% accuracy, whether a customer is likely to default next month. 

If the balance of recall and precision is the most important metric, then Random Forest is the ideal model. 

## Reference
1. Machine Learning Mastery 
2. Geeks for Geeks 
3. Analytics Vidhya
## 🚀 About Me


- 👋 Hi, I’m Manikanta, a curious Data Dcientist
- 👀 I’m currently working on Machine Learning projects.
- 💞️ I’m would love to collaborate on Machine Learning projects.
- 📫 How to reach me : manipavangmanipavang637@gmail.com
- 👀 LinkedIn : https://www.linkedin.com/in/manikanta22/
