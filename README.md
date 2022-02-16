# Credit Line Increase Model Card

Date: 15 February 2022<br>
● Model Version: 1.0<br>
● License: MIT License<br>

# Intended use:<br>
**Intended Uses**: This model's intended use is for educational purposes only. This<br>
model is an example of probability, with a sample use case for defining eligibility<br>
for a credit line increase.<br><br>
**Intended Users**: Students in GW’s DNSC 3288W <br>
- Out of Scope Users: Any use beyond an educational purpose by the group<br>
members is out-of-scope<br>

# Training data<br>


- Data Dictionary


Name | Modeling Role | Measurement Level | Description 
--- | --- | --- | --- |
ID | ID	|int|	unique row indentifier | 
MIT_BAL | input	|float|	amount of previously awarded credit|
SEX | demographic information	| int|	1 = male; 2 = female | 
RACE | demographic information|	int|	1 = hispanic; 2 = black; 3 = white; 4 = asian| 
EDUCATION | demographic information	|int |	1 = graduate school; 2 = university; 3 = high school; 4 = others |
MARRIAGE | demographic information	| int |	1 = married; 2 = single; 3 = others |
AGE | demographic information	| int	age in years | 
PAY_0, PAY_2 - PAY_6 |inputs|	int	| history of past payment; PAY_0 = the repayment status in September, 2005; PAY_2 = the repayment status in August, 2005; ...; PAY_6 = the repayment status in April, 2005. The measurement scale for the repayment status is: -1 = pay duly; 1 = payment delay for one month; 2 = payment delay for two months; ...; 8 = payment delay for eight months; 9 = payment delay for nine months and above|
BILL_AMT1 - BILL_AMT6 |inputs |	float	| amount of bill statement; BILL_AMNT1 = amount of bill statement in September, 2005; BILL_AMT2 = amount of bill statement in August, 2005; ...; BILL_AMT6 = amount of bill statement in April, 2005|
PAY_AMT1 - PAY_AMT6 | inputs |	float	| amount of previous payment; PAY_AMT1 = amount paid in September, 2005; PAY_AMT2 = amount paid in August, 2005; ...; PAY_AMT6 = amount paid in April, 2005|
DELINQ_NEXT | target | int |	whether a customer's next payment is delinquent (late), 1 = late; 0 = on-time| 

**Source of Training Data:** Provided by Professor Hall<br><br>
**How training data was divided into training and validation:**<br>
- 50% training<br>
- 25% validation<br>
- 25% test<br><br>
**Number of rows in training and validation data:**  
- Training rows: 15000. 
- Validation rows: 7500. 

# Model details
Columns used as inputs in the final model:<br>
- 'LIMIT_BAL', 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6', 'BILL_AMT1', 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4',<br>
- 'BILL_AMT5', 'BILL_AMT6', 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5', 'PAY_AMT6'<br>
- Column(s) used as target(s) in the final model: 'DELINQ_NEXT'<br>

# Type of model: Decision Tree<br>
- Software used to implement the model: Python, scikit-learn
- Version of the modeling software: 0.22.2.post1

# Model details<br>
Columns used as inputs in the final mode:<br>
- 'LIMIT_BAL', 'SEX', 'RACE', 'EDUCATION', 'MARRIAGE', 'AGE',<br>
- 'PAY_0', 'PAY_2', 'PAY_3', 'PAY_4', 'PAY_5', 'PAY_6', 'BILL_AMT1',<br>
- 'BILL_AMT2', 'BILL_AMT3', 'BILL_AMT4', 'BILL_AMT5', 'BILL_AMT6', <br>
- 'PAY_AMT1', 'PAY_AMT2', 'PAY_AMT3', 'PAY_AMT4', 'PAY_AMT5',<br>
- 'PAY_AMT6'<br>

Columns used as targets:<br>
- 'DELINQ_NEXT'’<br>

Type of model:<br>
- Decision Tree Model<br>

Software used to implement model:<br>
- Python and sk learn<br>

Version of modeling software: <br>
- (Python) Version 3.7.12<br>

Hyperparameters:<br>
- max_depth=6, random_state=12345
