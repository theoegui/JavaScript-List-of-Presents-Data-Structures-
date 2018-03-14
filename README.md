# JavaScript-List-of-Presents-Data-Structures-
A JavaScript Data Structure Problem that uses arrays, math methods, and if statements and for loops. Your using FUNDAMENTALS ARRAYS LISTS of DATA , Data STRUCTURES, LOOPS, CONTROL FLOW, BASIC LANGUAGE FEATURES ALGORITHMS.

Task:
Leo's girlfriend asked him to buy a gift list during his next trip, now he wants to know how many of them will he be able to buy.

Write the following function to help Leo out:

function howManyGifts(maxBudget, gifts)
The first parameter is Leo's budget; he second one is an array (a list in Groovy) containing the price of each gift. You should return an integer representing the maximum amount of gifts Leo can buy.

Example:
Maximum budget: 20
Gift List: [13, 2, 4, 6, 1]
Should return 4.

NOTE: All numbers will be integers >= 0, and the array will never be empty.

function howManyGifts( maxBudget, gifts ) {
	
	var newBudget = maxBudget;
	var Giftcount = 0;

 
	// While we have enough money and there is at least one more gift to buy on the list
	while ( newBudget > 0 && gifts.length > 0 ) {
		
		// Let's find the cheapest gift on the list
		var cheapGiftIndex = 0;

		for ( i = 0; i < gifts.length; i++ ) {      
      if ( gifts[ i ] < gifts[ cheapGiftIndex ] ) {
        var cheapGiftIndex = i;
      }
		}

		// After the above for loop ends, cheapGiftIndex will point to the least expensive gift on the list
    // Remember, the price of that gift can be accessed with: gifts[ cheapGiftIndex ]

		// Now let's try to buy this gift
		newBudget = newBudget - gifts[ cheapGiftIndex ];

		// Did we spend more money than what we had in our wallet?
		if ( newBudget < 0 ) {
			// YES: stop everything and return the counter
			return Giftcount;
		}
		else {
			// NO: increment the counter...
			Giftcount++; 

			// ... and take the gift off the list
			gifts.splice( cheapGiftIndex, 1 );
		}
	} // end while
  
  // Return the counter  
  return Giftcount;

} // end function

var B = howManyGifts( 20, [ 13, 2, 4, 6, 1 ] );
console.log( B );
