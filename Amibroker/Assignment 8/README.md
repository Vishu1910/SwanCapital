This particular folder involves the codes for "Strike Selector" and "Execution" of codes.

**1. Strike Selector Code**
    
   The strike selector code aims to get the symbols which we wish to buy.
   We perform this operation on the watchlist where all our Option Symbols are present.
   First, we get the open and close values for all the symbols present in the watchlist with different symbol names. 
   We set the reference as **BankNifty** to get the closing price of 1 recent bar of the same and then get the ATM value.
   For the value so obtained, we round it to the nearest whole number and assign a static variable unique to the symbol, as we wish to buy/sell that particular symbol.
   We check for the different criterias - if the Name in our watchlist is equal to the symbol so formed, if the above defined static variable is 0, number of symbols in the watchlist are lesser than the desired number of symbols.
   And then add the symbol if all conditions are true. Now, we increase our counter by 1 and set the static variable defined to the unique symbol as 1; so that it does not get added multiple times and number of symbols are lesser than or equal to our condition check.
    
   (We perform the same operation for **Nifty50** symbols too)
  
**2. Execution Code** 

  The Execution Code is used for placing/modifying the orders that we selected from our Strike Selector code.
  We perform this operation on the watchlist where we have the symbols selected from above.
  Once the order is placed for a particular symbol, we fetch the order ID for the same and make sure that the order does not go twice or more for the same symbol.
  If the order hasn't been filled, we modify the order for that particular symbol (once or more than once) till the order status is filled.
  
