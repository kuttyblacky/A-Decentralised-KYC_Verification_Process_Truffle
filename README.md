# A-Decentralised-KYC_Verification_Process_Truffle

Origin of KYC

Know Your Customer, aka KYC, originated as a standard to fight against the laundering of illicit money flowing from terrorism, organised crime and drug trafficking. The main process behind KYC is that government and enterprises need to track the customers for illegal and money laundering activities. Moreover, KYC also enables banks to better understand their customers and their financial dealings. This helps them manage their risks and make better decisions.

 

Need for KYC

Taking in from the origin of KYC, we can state that there are four major sectors in banking where KYC is needed:

Customer Admittance: Restricting the entry of anonymous accounts into the banking system. In other words, no anonymous accounts are allowed. Preliminary information such as names, birth dates, addresses and contact numbers is to be collected to provide banking services.

Customer Identification: In case of suspicious banking transactions by a customer, the customer's account can be tracked and flagged. Further, it can be sent to process under the bank head office for review.

Monitoring of Bank Activities: The bank can zero in on suspicious activities in any account after understanding its customer base using KYC.

Risk Management: Since a bank has all the preliminary information and activity patterns, it can assess the risk and likelihood of a customer being involved in illegal transactions.

 

These requirements make the KYC process an essential entity in the banking and financial world. A traditional KYC process is already in place in the banks, but there are major challenges in the process. Through this case study, we will assess and tackle these challenges. Let us first list out the challenges related to the traditional KYC process.

 

Problems/Challenges in KYC
Disparity in the Specifications for KYC:

Every bank has its own KYC process setup, and customers need to undergo KYC verification again and again for each bank.

Due to lack of KYC standards, compiling reach request is time consuming.

Adverse impact on Customer relationship:

It becomes irksome for the customers to provide the same information to different banking entities and industries.

Banks sometimes even follow up with customers to get more details for KYC.

Escalating Costs and Time for Banks:

A recent study concluded that the overheads of KYC for a bank increase the onboarding cost for a customer by 18% and the minimum time required to 26 days. 

Solution using Blockchain
Blockchain is an immutable distributed ledger shared with everyone involved in a network. Each participant interacts with the blockchain using a public-private cryptographic key combination. Moreover, immutable record storage is provided, which is very hard to tamper with.

 

Banks can utilise the feature set of blockchain to reduce the difficulties faced by the traditional KYC process. A distributed ledger can be set up among all the banks, where one bank can upload the KYC of a customer and others can vote on the legitimacy of the customer's details. The KYC for the customers will be stored immutably on the blockchain and will be accessible to all the banks in the blockchain.

 

This case study is divided into three phases to achieve the solution.

Phase 1:
Whenever a new customer enters the ecosystem, a bank initiates a KYC request for the customer .

Once checked for veracity, the bank uploads the customer's data onto the blockchain using the smart contract.

Whenever any new data needs to be appended, the ledger could enable encrypted updates to the ledger. Mining will make sure the data gets confirmed over the blockchain and is distributed to all the other banks.

The KYC data can be accessed by the other banks in real-time as and when required.

Other banks can vote on the KYC process followed by a bank for a customer in order to state that they acknowledge the process and accept the customer's details.

Phase 2:
Admin functionalities are provided for the system, where an admin can track the actions performed by banks, such as uploading or approval of KYC documents.

Other banks can vote on the KYC process followed by a bank for a customer. If their ratings/votes are above the standard range, then it is taken as an accepted KYC process and is used by other banks as well.

The banks also vote over the other banks to make sure that the banks are secure and not tampered for the KYC process. This identifies whether a bank has become corrupt and is uploading fake customer KYC. This rating will help the bank's assess each other's activities, and remove fraudulent banks from the network.

The admin can block any bank from performing a KYC. The admin can also add new banks or remove untrusted banks from the smart contract.

Phase 3:
In this phase, the smart contract will be deployed over a private network, which is set up between various banks.

The banks can use the functionalities of the smart contract over this private Ethereum network.

The banks need to have an account on the private network to interact with the smart contract.

 

You need to solve only Phase 1 here. Phase 2 and Phase 3 constitute the Course Assignment. Phase 1 is the pre-requisite for Phases 2 and 3. You will take a look at Phases 2 and 3 in detail in the next module on the Course Assignment. Although the solution for Phase 1 is provided at the start of the module on Course Assignment, it is highly recommended that you try to solve Phase 1 on your own before looking at the solution. 

 

Details of Phase 1

 Bank accounts and bank functionalities
There are two types of Accounts that can exist in your Ethereum network: admin and banks. There will be only one admin account and multiple bank accounts. Only the admin can add or remove a bank. Admin functionalities, including adding/removing banks, will be covered in Phase 2. In this phase, we will only cover banks and the functions that they can call. Banks have the following functionalities:

To add the KYC request of a customer to the KYC_requests list: Once a customer requests a bank to do their KYC, the bank will add the request to the KYC_requests list on the blockchain. Any bank can pick up a KYC request from the list and then verify the KYC documents. 
To add a customer to the customer list: Once a bank verifies the KYC documents of a customer, it adds the customer to the global customer list on the blockchain.
To remove a KYC request from the KYC_requests list: If a verification is successful and the customer is added to the list, then the KYC request of the customer is removed from the KYC_requests list. If the verification fails, nothing is done. Any other bank might pick up the request and perform the verification.
To remove a customer from the customer list: For Phase 1, any bank can remove any customer irrespective of who added the customer and whether the customer's details are verified by multiple banks or not. If a particular bank feels that a customer has been wrongly added to the customer list and KYC was not done correctly, then the bank can remove the customer from the customer list.
To vote for a customer: A bank can upvote for any customer present in the customer list. If the number of upvotes for a customer is above a certain number, then the customer is added to the verified_customers list. For Phase 1, you do not need to create a verified_customers list. You only need to provide the functionality to banks where they can upvote for a customer, thereby acknowledging that they accept the KYC process for him or her.
To modify the details of a customer.
 

Bank and Customer Details

A customer is stored as a struct type. The customer struct needs to have the following components: 

Username of the customer: Username is provided by the customer and is used to track the customer details. 
Datatype: string.
Customer data: This is the hash of the data or identity documents provided by the Customer. 

Datatype: string.

Upvotes - This is the number of upvotes received from other banks over the Customer data.

Datatype - unsigned Integer

Bank: This is the unique address of the bank that validated the customer's account.

Datatype: address.

Similarly, you need to create a bank struct. The bank struct will have the following components: 

Name: This variable specifies the name of the bank/organisation:

Datatype: string

ethAddress: This variable specifies the unique Ethereum address of the bank/organisation:

Datatype: address

regNumber: This is the registration number for the bank:

Datatype: string

Similarly, a KYC request will have the following components:

Username of the customer: Username is provided by the customer and is used to track the customer details. 
Datatype: string.
Customer data: This is the hash of the data or identity documents provided by the Customer. 

Datatype: string.

BankAddress: Bank address here is the unique account address for the bank, which can be used to track the bank.  This is the unique address of the bank that initiated the KYC request. 

Datatype: address.

Use case
After a user gives consent to share their KYC data with a bank, which could be in digital format, like a pdf, jpg or doc file, the following steps will take place:

The bank will check the blockchain to fetch the hash of the data and use the hash to fetch the actual data from a secure storage.

The bank will update the KYC data if required.

If data is not already present with the smart contract, then the bank will create a new request to add the KYC of the customer.

 

                 

 

 

 

Functions for banks in your smart contract
The following are the functions that you need to write in your smart contract. These functions are the same as the ones mentioned above: 

Add Request: This function is used to add a KYC request to the requests list:

Parameters: Customer name as a string and the hash of the customer data as a string.

Return: A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

Add Customer: This function is used to add a customer to the customer list:

Parameter: Customer name as a string and the hash of the customer data as a string.

Return: A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

Remove Request: This function is used to remove requests from the requests list:

Parameters: Customer name as string.

Return: A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

Remove Customer: This function is used to remove a customer from the customer list:

Parameters: Customer name as string.

Return: A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

Modify Customer: This function allows a bank to modify a customer's data. For Phase 1, any bank can modify the data. This is applicable only to customers whose requests have been validated and who are present in the customer list:

Parameters: Customer name as string, and the new hash of the new customer data as string.

Return:  A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

View Customer: This function allows a bank to view the details of a customer:

Parameters: Customer name as string.

Return: The function will return hash of the customer data in string format.

Upvote: This function allows a bank to cast an upvote for a customer. This vote from a bank means that it accepts the customer details and also acknowledges the KYC process done by some bank on the customer. 

Parameters: Customer name as string.

Return: A flag can be returned as an unsigned integer, value '1' to determine the status of success or value '0' for the failure of the function.

Smart contract flow
The bank collects information for KYC from a customer.

The information collected includes a unique Customer User Name and Customer data, which is the hash link for the data present in a secure storage.

The bank creates a KYC request for submission, which is stored in the smart contract.

This requests is then taken up, and after verification, the customer is added to the customer list.

For a bank to acknowledge that it accepts the customer details, it needs to cast an upvote for the purpose.

