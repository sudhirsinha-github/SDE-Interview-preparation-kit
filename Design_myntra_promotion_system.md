



## Design a promotion offer service & system ::

Coupon - code for customer to get discount - instant /cashback

Primary Features 
1. apply Coupon
2. remove Coupon
3. list Coupon


Coupon{
    desc -
    code -
    type - 
    start -
    expiry -
}

Rule Engine
list of Coupon - Mobile order
GHS orders.


Services 

Coupon
  -generate
  - list
  - remove
  - Adhoc - expire before actual expiry (misuse, leaked)
  ### - Apply ( validate )

Rest API

Admin -

GET /coupons

GET /coupon/id


POST /coupon

Update only expiry date -forcefully (not put)
PATCH /coupon/id

PUT /coupon/id

customer
Fetching coupon details
GET /coupon?code=12xxww


rule Engine
userid 
ordertotalAmt
coupon_id
product_id
productcategory 


coupon -> get details 
product -> produ

```js
##scehema
sql

coupon{
id
code
desc
expiry
start
value 
status - active, inactive (stop for given day/s)
createdOn,by
UpdateOn,by
min/maxAmount
platform -phoneApp,website..
MaxUsersApplied -100
MaxPerUsers -10x
}

rule_engine
{
coupon_id
userid
product_id
productcategoryID
createdOn...
}

```


![image](https://user-images.githubusercontent.com/16834697/123419846-5a536880-d5d8-11eb-881e-789a42c7617e.png)
