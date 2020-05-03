# MoneyDock_Srapi DEV. API

## Products

### GET	/home
* Get all brief products information 

``` 
  {
  	"products": [{"_id":XXX, "name":"Iphone", "img":XXX, "bid_price":400},
   				{"_id":XXX, "name":"Surface Pro", "img":XXX, "bid_price":850}]
  }
```

### GET /products/:productId
* Get Single Product detail page

```
	{
		"_id": XXX,
		"name": "Iphone",
		"goal": 420
		"condition": "good",
		"description": "This is a great Iphone!",
		"address": "Tucson, USA",
		"preference": "in person"
		"bid_histroy": [
						{"user": Object,	"bid": 120},
						{"user": Object,	"bid": 400},
						{"user": Object,	"bid": 450},
		]
	}

```

## User

### POST /user/signin
* User sign in

```
	{
	    "email": "jack@gmail.com",
	    "password": "jasck",
	    "connection": "Username-Password-Authentication",
	    "user_type":"personal_user",
	    "client_id":"vZa_xsdgwAar0KiP9my-G3dsKt5kBuBY" 
	}

```

### POST /user/signup
* User sign up 

```	
	{   
		"username":"JACK",
	    "email": "jack@gmail.com",
	    "password": "jack",
	    "connection": "Username-Password-Authentication",
	    "user_type":"personal_user",
	    "client_id":"vZa_xsdgwAar0KiP9my-G3dsKt5kBuBY" ,
	    "method":"create"
	}
```

### GET /user/:userId
* Get basic the user information

```
	{
		"_id": XXX,
		"name": "Shiyu_2020",
		"email": "shiyu@gmail.com"
		"img": XXX
	}
``` 

### GET /user/signout
* User sign out

## Buyer Side

### GET /user/buyer/:userId
* Get the user's deal histroy (successed, processing, failed) as a buyer

```
	{
		[
			{"_id": XXX, "procedure": "processing", "product": Object},
			{"_id": XXX, "procedure": "successed", "product": Object},
			{"_id": XXX, "procedure": "failed", "product": Object},
		]
			
	}
```

### POST /user/product/:userId/:productId
* Post bid price

```
	{   
		"userId": "XXX",
		"productId": "XXX",
		"bid": 450
	}
```

### PUT /user/edit/:userId
* Update user information 

```
	{
		"_id": XXX,
		"name": "Rose_2020",
		"email": "rose@gmail.com"
	}
```

### DELETE /user/buyer/:userId/:dealId
* Delete the deal that the buyer does not want any more

### DELETE /user/:userId
* Delete user account



## Seller


### GET /user/seller/:userId
* Get the user's posted products (successed, processing) as a seller

```
	{
		[
			{"_id": XXX, "procedure": "processing", "product": Object},
			{"_id": XXX, "procedure": "successed", "product": Object},
		]
			
	}
```


### POST /user/seller/:userId
* Post products as a seller

```
	{
		"seller_id": 6,
		"name": "iphone XR",
		"condition": "good",
		"category": "mobile",
		"goal_price": "100",
		"Description": "a used iphone XR"
	}
```


### PUT /user/seller/confirm/:userId/:dealId
* Confirm the bid deal


### PUT /user/seller/cancel/:userId/:dealId
* Cancel the bid deal


### Delete /user/seller/:userId/:dealId
* Delete the bid deal

### DELETE /user/seller/:userId/:productId
* Delete the product that the seller dose not wanna sell anymore
