# Ironhack Project - Bank Case Study

## Table of Contents
- [Project Overview](#Project-Overview)
- [Project Brief](#Project-Brief)


## Project Brief

**Scenario:** We are risk analysts employed at a bank. The bank is interested in identifying 'good' and 'bad' customers and we are tasked with identifying them.

**Challenge:** Use the given data set to identify the characteristics which can be used to identify 'good' and 'bad' customers.

**Problem:** Can we create a machine learning model which can effectively identify 'good' and 'bad' customers?


## Defining the problem

In order to tackle this issue, we had come up with a way of defining 'good' and 'bad' customers. We decided to define this using the 'Status' column within the data.

'Good' customers would have statuese of A: 'contract finished, no problems' or C: 'running contract, OK so far'. 

'Bad' customers would be have statuses of B: 'contract finished, loan not payed' or D: stands for running contract, client in debt.


## Process & Tools

### Github

The project was stored and updated via github.

### SQL

I started by accessing the bank data in SQL by running a [script](https://github.com/zachighton/example_layout/blob/main/bank_sql_dump_script.sql). Then wrote a [query](https://github.com/zachighton/example_layout/blob/main/bank_sql_query.sql) to access the relevant features, which I could use for the analysis.

### Python

**Import:**

I then imported the data into python to begin exploratory analysis. The link to the jupyter notebook can be found [here](https://github.com/zachighton/example_layout/blob/main/log_regression_bank.ipynb).

**Cleaning:**

The first step was to clean the data.
- simplifying and combining columns
- correcting for typos
- filling in blanks with 'unknown'
- removing null values
- change data types (some numerical data was better processed as objects)

**Normalisation:**

Once this was complete I moved on to normalising the data so that it could be better processed by the model.

**Modelling:**

The final stage was to model the data using logistic regression. I then evaluated the model using various metrics to assess how well it wa able to categorise customers.

## Visualizations

<img width="400" alt="Screenshot 2021-11-10 at 16 53 53" src="https://user-images.githubusercontent.com/89530964/141146633-465d0271-c077-499d-8c11-b615ff54caa3.png">
<img width="400" alt="Screenshot 2021-11-10 at 16 56 24" src="https://user-images.githubusercontent.com/89530964/141147130-c7c000aa-6ff5-4f1f-8d33-9168ab6fa02e.png">


## Key Take Aways

With the data I currently have access to, I am not able to accurately predict whether customers are 'good' or 'bad' for the bank.

Using the accuracy_score metric from sklearn, the model achieved an accuracy of 88%. This appears to be a good result. However, when we look at the confusion matrix, we can see that although the model is very good at predicting 'good' customers, it also often misassigns 'bad' customers as 'good' customers.

This is shown in the AUC score, which was 73%. Although, not an awful score, there is a lot of room for improvement.

The issue here appears to be that since there are many more 'good' customers at the bank than 'bad' customers, the model is over prioritising that group in the model.


## Next Steps

The obvious next step would be to rerun the model having done some sampling techniques. If we were to over or under sample from the original data, to even out the number of 'good' and 'bad' customers that the model recieves, we may be able to get fewer false negatives.





