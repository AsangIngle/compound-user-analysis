1 Overview
This project finds out how wallet IDs interact with the Compound DeFi protocol using data from the Covalent API. It gives each wallet a score based on its behavior.

2 Data Collection Method
1 The wallet addresses were read from a file called Sheet1.csv
2 For each wallet, transactions were fetched using the Covalent API
3 Only transactions related to Compound tokens like cETH, cDAI, and cUSDC were selected
4 These filtered transactions were saved in a file named compound_wallet_transactions.csv

3 Feature Selection Rationale
1 Total number of Compound-related transactions
2 Number of different Compound contracts used
3 Total value transferred using Compound transactions
4 Average gas used in Compound transactions
5 Time duration between the first and last Compound transaction
6 Frequency of transactions during the active period

These features were saved in compound_wallet_features.csv

4 Scoring Method
1 All features were scaled between 0 and 1 using min max scaling
2 Each feature was given equal importance
3 A final score was calculated by adding all normalized features
4 Higher scores mean more active and trustworthy wallets

5 Justification of the Risk Indicators Used
1 More activity and higher value may show trusted or regular users
2 Using many Compound contracts shows the user understands the platform
3 High gas usage might mean complex operations like lending and borrowing
4 Very few or short-term activities might mean less trustworthy or automated users

These indicators were used to judge and score each wallet

6 Deliverables
1 compound_wallet_transactions.csv
2 compound_wallet_features.csv
3 compound_wallet_scores.csv

7 How to Run
1 Make sure you have a file named Sheet1.csv with wallet addresses
2 Run the Python script
3 The output files will be created in the same folder

8 Requirements
1 Python version 3.7 or above
2 pandas
3 requests
4 scikit-learn