# Response codes

API follows standard HTTP status codes for success or failure of an API call. Below table desribes the possible code responses.

|            Status         |        Code description      |
|---------------------------|------------------------------|
|200 - OK                   | Meal ordered successfully.   |
|429 - Too Many Requests    |Too many orders come in at the same time.|
|500 - Internal Server Error| A generic error message when there is an issue with the server.|
|440 - Login Time-out       |The client's session epires when they taketoo long to order. Items cannot sit at the order stage indefinitely.|
|404 - No response           |The server cannot find the requested resource.|
