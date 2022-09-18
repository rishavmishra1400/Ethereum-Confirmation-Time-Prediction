
# Confirmation Time Prediction in Ethereum

When a user makes an exchange of ether or execute
a contract it is considered to be a Transaction.

Due to the importance of these transactions it is
very important for a user to gain some insight on how
much time it might take for the transaction to be
processed based on the network traffic.

By gaining
these insights ahead of time, a user can infer whether
right now would be the right time for them to send this
transaction to the network.
## Components Of Transaction


- Transaction value
Amount of Ether to be transferred 
- Basefees
The Base Fee is determined by the Ethereum network depends upon number of miners seeking to validate transactions
- Maxfees per gas
The Max Fee is the absolute maximum amount you are willing to pay per unit of gas to get your transaction confirmed
- Miners Tip
The part of transaction fees directly sent to miner, miner sort the transaction in order of tip
- Transaction fees
The fees user should pay to get the transaction confirmed
- Gasusage
Amount of gas that was used to execute 
a transaction.
- Gaslimit
Represents the maximum amount 
of gas that can be used to execute 
a transaction.
- Gasprice
     
Amount be paid per unit of gas for the computation cost incurred due to 
the execution of a transaction

- Etherprice	

- Burnt value

- CompletionTime
The time taken for the transaction get added into a mined block

## Data collection
The data was extracted from ethereum.io

the following selenium code was used for extraction

for each transaction one request


For each data field In our data set, that is one transaction One request was sent to etherscan, one webpage was loaded, and the data was scraped .

We were trying to create a big data set. We needed a lot of transaction data. So the extraction of one transaction should be fast.

The standard limits the number of requests sent in one minute by one user to 100.

Running the script in headless mode was the next step to doing so. That occupied all of their computational resources 




One option was to run these Selenium scripts on virtual machines for free and to make them run 24/7. We used 10 virtual machines and ran the scripts simultaneously.

Relpit provides free virtual machines for web servers.

10 servers were created on the Relpit program, which was extracting ethereum data and storing it in Google sheets. The Google Sheets API is also used for this.




These 10 servers were hosted and running 24 hours a day, which made the whole extraction process 10 times faster.


## Screenshots
- Running server on www.replit.com virtual machine
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/1304592586a84a60d20a16c03a312c6aa4aeadbc/Screenshots/Server%20Running%20on%20Virtual%20machine.png)


- Monitoring the servers using www.uptimerobot.com and also ping in every 5 mins
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/1304592586a84a60d20a16c03a312c6aa4aeadbc/Screenshots/Monitoring%20the%20runtime%20of%20servers.png)



- Each transaction stored as
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/main/Screenshots/Data1.png)
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/main/Screenshots/Data2.png)

## Proposed Model

Random forest model, in general, performs well at 
learning complex, highly non-linear relationships; like 
between time and both the gas price and the gas used 
in Ethereum blockchain dataset.

The model is known 
to outperform fundamental classification and 
regression models like naïve Bayes, polynomial and 
linear regressors. The model proposed in the 
paper employs random forest regressor to make 
confirmation time predictions. 

## Hyperparameter tuning in Random forest
RandomizedSearchCV implements a randomized search over parameters, where each setting is sampled from a distribution over possible parameter values. 

A random forest uses many parameters
- n_estimators
- max_features
- max_ depth
- min_samples_split
- min_samples_leaf

We found the best parameters by RandomizedSearchCV
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/main/Screenshots/BestParams.png)

## Evaluation of the model

Accuracy of the model on both training and test dataset was tested
![App Screenshot](https://raw.githubusercontent.com/rishavmishra1400/Ethereum-Confirmation-Time-Prediction/main/Screenshots/Accuracy%20of%20model.png)

The model was trained with 135,712 transaction

and was tested on 33,928

Train Data Accuracy = 70.75%
Test Data Accuracy = 77.18%

Since millions of transaction are done on ethereum blockchain everyday . So the further improvement on the model can be performed by adding more data samples to the training data.
