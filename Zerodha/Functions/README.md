This file contains all information related to how to set the access token for zerodha login, how different functions are used and what parameters are required for those functions.

How to get Access Token - 
1) We fetch the APIkey and APISecret from our Zerodha account. Using a URL, we get our Request Token key which is then provided as an input to the function "LOGIN()".
2) The Login() function so defined returns us the access_token which expires after 24 hours. We repeat the same process every day while logging in for the first time in the morning.
( We can have this access_token stored as a static variable which can then be called in different programs )

Functions -
After fetching the access token, we can place/modify/cancel orders based on this access token and various other parameters.
Functions to be used for Zerodha plugin : 
1) Login(requesttoken,APIkey,APIsecret) - returns access token which we then need to use throughout that day. 
2) PlaceZerodhaOrder(APIkey,accesstoken,exchange,tradingsymbol,transactiontype,quantity,price,product,ordertype,validity,disclosedquantity,triggerprice,squaredoffvalue,stoplossvalue,trailingstoploss,variety,tag) - returns an Order ID if all parameters mentioned are valid
3) GetOrdersById(orderID,accesstoken,APIkey) - returns the details of the order filtered by ID
4) GetOrder(accesstoken,APIkey) - returns the details of all orders pertaining to that particular apikey
5) CancelZerodhaOrder(APIkey,accesstoken,OrderID,Variety,ParentOrderID) - returns the Order ID after order cancellation is completed
6) ModifyZerodhaOrder(APIkey,accesstoken,OrderID,ParentOrderID,Exchange,TradingSymbol,TransactionType,Quantity,Price,Product,OrderType,validity,DisclosedQuantity,TriggerPrice,Variety) -
7) GetZerodhaHoldings(apikey,accesstoken) - returns the data for all the holdings corresponding to the particular api_key
8) GetZerodhaPositions(apikey,accesstoken) - returns the data pertaining to the positions held.

