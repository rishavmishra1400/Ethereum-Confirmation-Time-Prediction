
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
- Burnt value
- Basefees

- Maxfees per gas
- Miners Tip
- Transaction fees
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



- CompletionTime

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







