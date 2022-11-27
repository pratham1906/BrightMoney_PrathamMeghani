## Pratham Meghani
## Bright Money Assignment


```sh
$ pip3 install -r requirements.txt
```
  
## Install RabbitMq (for Async Message Queue)

```sh
$ - wget -O- https://dl.bintray.com/rabbitmq/Keys/rabbitmq-release-signing-key.asc | sudo apt-key add -
```
```sh
$ - wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
```
```sh
$ - sudo apt-get update
```

### Install
```sh
$ sudo apt-get install rabbitmq-server
```

```sh
$ python3 manage.py makemigrations
```
```sh
$ python3 manage.py migrate 
```
```sh
$ python3 manage.py runserver
```
  
##  Celery   

```sh
$ celery -A Plaid_Manager_API worker -l info
```

 
  
### All API Related To users
  
-  users/register/ -> User-Register-API  
-  users/login  -> User-Login-API  
-  users/logout/  -> User-Logout-API  
  
### API For Token Exchange 
  
POST REQUESTS 
  
-  token_exchange/link_token/ -->> Get-Plaid-Link_Token 
-  token_exchange/get_access_token/ -> Plaid-Link-Public_token (exchange public token with access_token)  
  
[GET req]  
  
-  token_exchange/home/  -----> Get-Public_token 
-  token_exchange/get_items/	-----> Get-All-Items  
-  token_exchange/get_accounts/ -> Get-All-Accounts 
-  token_exchange/get_transactions/ -->  Get-All-Transactions  
-  token_exchange/transaction_webhook/ -> Transaction-Webhook  



## sCHEMA/Model Details:


## Model stuff as per given in problem statement 


### BankItemModel
  
-	bank_item_id
-	access_token
-	request_id
-	user  
  
### AccountModel
  
-	account_id
-	bank_item
-	balance_available
-	balance_current

### TransactionModel
  
-	transaction_id
-	account
-	amount
-	date
-	name
-	pending
  
### APILogModel

-	request_id
-	api_type
-	date_log
