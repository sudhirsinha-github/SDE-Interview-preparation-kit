



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
```
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
```

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




Things to consider for any design/checklist

```
1. Functional requirements 
2.nfr
3. Capacity estimates - calculate 
4. Hld 
5. Db schema sqlvs nosql
6. Rest api
7.component design LLD
8. Db partitions sharding
9. Scaling - Vertical and horizontal 
- Microservices Architecture 
9. Monitoring,Alerts
10. Improvments
```


```
00:00:00 Introduction
00:00:44 Design a reservation and payment system for a parking garage
00:01:08 Product requirements
00:03:11 Public endpoints
00:05:47 Internal endpoints
00:09:35 Scale Discussion
00:11:11 Data schema
00:20:06 High-level architecture
00:23:31 Trade-offs
00:26:48 Interview feedback
00:28:39 Advice for similar questions
```
