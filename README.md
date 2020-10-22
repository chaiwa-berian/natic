A core banking platform is a digital application that  supports the processing needs of a bank to provide financial products and services to customers. 

Lets use Jane's banking needs as an example to better understand what a core does for the bank to provide financial services to Jane. 

Jane walks into the bank and asks for a checking account. The banker requests some PII information and makes Jane sign some boring paperwork. Minutes later, the banker provides Jane a nice new debit card and an account number. Jane leaves on her merry way and now has a bank account!  Every week her payroll is deposited into her account increasing the balance on the account. When Jane uses her debit card to buy dinner, her account balance decreases. Every financial event is captured and reflected by her bank in her account. 

When the banker entered Jane's information in the core,  her personal information was stored creating a customer record, an account record was created and linked to Jane's customer record creating Jane’s relationship with the bank. Each time Jane was paid, the core processed ach file with instructions to deposit funds into Jane's account. Each time Jane used her debit card, the core received a file requesting money be withdrawn from her account. 

To over simplify, the core is processing simple CRUD operations. 

Create - Jane's information is created in the core.

Read - ACH/Debit card files are read from an alternative data-source.

Update - Jane's account balances are updated. 

Delete - (We wont use delete in banking but will use INACTIVATE). If Jane closed her account, the account becomes inactive in the core. 

So from a high level this is what a core needs to do. However, there are MANY moving parts to fully developing an all in one solution for this.  

Specifications

Product specifications will be broken down in many levels as each specification will have child specifications. To capture and break down specifications over time we can start with the highest level and work our way down. 

Product Specifications Level - 1

Specification

Bank Story

BaaS Story

01 - Customer/Entity  Records

Customer information needs to be captured. Customers can be business, people or portfolios.  People have relationships with people, businesses and portfolios. Relationships need to be tracked and can be recursive. For the 

Fintechs need to capture FBO (For Beneficiary Owner) records. Similar to Bank Story however, may need a UUID to join to a master relationship. 

02 - Products

Banks offer many products and services. The application should support managing the products and services offered while enabling implementing business logic. Products define the parameters available to accounts.

Products differ here. These are an api abstraction of the Bank Story

03 - Accounts

Accounts both customer and internal General Ledger. Capture all financial events that occur on an account. 

04 - Transactions 

