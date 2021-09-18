# Deposit Calculator for Accomdation Taxes + Rate
**This is just pretty crude and simple javascript I wrote for self-use to automate tedious calculations I'm preforming nightly at work.
This probably will never serve any real world purpose except meeting a need of an extremely niche group that is made up of myself and that's it lol**

My hotel collects 3 separate taxes (6%, 5%, and 2%). Our systems aren't setup to calculate the proper amount we are to collect for advance deposits. This could be fixed
but progress is slow as I don't have access to fix it myself. In the mean time we do the math and collect the deposit by hand. The *quick* steps everyone follows is to multiply
the sum of the nightly rates by 1.13. While correct for a 13% tax, our systems calculate and post each tax individually per night. Which leads to a lot of slight rounding differences
and requires and excessive amount of time constantly correcting. So I wrote a script to perform each calculation individually, round the numbers, and give me a sum in the same
manner that our systme posts the charges


## Breakdown
There are 3 files: the Static Rate Script, the Dynamic Rate Script, and the Webpage.

The *static rate* file is the bare bones basic algorithm. It will take two number inputs, one being the nightly rate and the second being how many nights the reservation is for.
The function then puts the nightly rate variable into an equation to mulitply by each tax rate and assigns a variable to each product. It rounds each of those products and assigns
them to a new variable. Those new variables are added back to the inputed rate and then mulitplied by the "length of stay" variable. The result is outputted to console

The *dynamic rate* file holds the function that allows multiple numbers to be entered when the funciton "rate()" is called. It pushes the numbers into an array and feeds each element
(rate) into the original function, outputs the each result into another array, and then ouputs the sum of the new array to console. This allows for quick calculation of a deposit
that is from a reservation that has a nighlty rate that changes each night.

The *webpage* file creates a webpage that allows for input from hmtl elements into the functions and outputs the results back onto the webpage
