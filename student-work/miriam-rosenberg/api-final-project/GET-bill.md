# Get/bill

The GET request is created when the customer requests a bill for their order as shown on the below code snippet. The GET request prompts the system to print the bill. All take out meals are assigned to table `99`. The objects of the oe sippet are explained in the Response Schema.

```
curl -X GET "http://URL/tableNo?id=99"  
#response 
{ 
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00", 
   "Item1":{ 
  	"ItemOrdered":{ 
     	"type":"burgerMeal", 
     	"Cost":10.99 
  	} 
   }, 
   "Item2":{ 
  	"ItemOrdered":{ 
     	"type":"salad", 
     	"Cost":9.50 
  	} 
   } 
} 
```

## GET/bill Response Schema

| Property Name | Data Type | Values                    | Definition                     |Value Variables|
|---------------|-----------|---------------------------|--------------------------------|---------------|
| orderNum      | int       |   123                     | Shows the order number of the day. The count resets at the beginning of each day.|Number increases with each additional order that comes in. There is an unlimited number of orders, but we can limit it to 10000 per day for the purpose of the app.|
| timestamp     | timestamp | 2020-01-21T07:44:45-05:00 |Shows the date of the order in YY-MM-DD format followed by the time when the bill was printed.|Changes depending on the day and the time.|
|Item1          |   int     |  "type" and "cost"        |Shows which item was ordered from the menu and the item's cost. There can be many items on one bill. Each consecutive item is marked with a higher number as `Item2`, `Item3` etc.| Varies depending on each customer's order. |
| type          |   int     | "burgerMeal"              | Shows the name of the meal ordered.      |Changes depending on what the customer orders.|
| Cost          |   float   |  10.99                    | Shows the cost of the meal item.         | Value depends on the price of each item.|
