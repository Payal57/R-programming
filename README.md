# R-programming(page no 7)
#2.1  Suppose you keep track of your mileage each time you fill up. At your last 6 fill-ups the mileage was
65311 65624 65908 66219 66499 66821 67145 67447
Enter these numbers into R. Use the function diff on the data. What does it give?
   > miles = c(65311, 65624, 65908, 66219, 66499, 66821, 67145, 67447)
> x = diff(miles)
You should see the number of miles between fill-ups. Use the max to find the maximum number of miles between
fill-ups, the mean function to find the average number of miles and the min to get the minimum number of miles.


> miles = c(65311, 65624, 65908, 66219, 66499, 66821, 67145, 67447)
>diff(miles)
>[1] 313 284 311 280 322 324 302
these values are the differences between the consecutive values.

>min(miles)
[1] 65311
>max(miles)
[1] 67447
>mean(miles)
[1] 66371.75
 
 
 
#2.2Suppose you track your commute times for two weeks (10 days) and you find the following times in minutes
 17 16 20 24 22 15 21 15 17 22
 Enter this into R. Use the function max to find the longest commute time, the function mean to find the average
 and the function min to find the minimum.
 Oops, the 24 was a mistake. It should have been 18. How can you fix this? Do so, and then find the new
 average.
 How many times was your commute 20 minutes or more? To answer this one can try (if you called your numbers
 commutes)> sum( commutes >= 20) What do you get? What percent of your commutes 
 are less than 17 minutes? How can you answer this with R?
 
 
 commutes=c( 17,16,20,24,22,15,21,15,17,22)
 max(commutes)
 [1] 24
 > min(commutes)
 [1] 15
 > mean(commutes)
 [1] 18.9
 > commutes[4]=18
 > max(commutes)
 [1] 22
 > sum(commutes>=20)
 [1] 4
 > sum(commutes<=17)
 [1] 5
 [(length(commutes)-sum(commutes<=17)]/length(commutes)*100
 [1] 50
 
 
 
 #2.3  2.3 Your cell phone bill varies from month to month. Suppose your year has the following monthly amounts
 46 33 39 37 46 30 48 32 49 35 30 48
 Enter this data into a variable called bill. Use the sum command to find the amount you spent this year on
 the cell phone. What is the smallest amount you spent in a month? What is the largest? How many months
 was the amount greater than $40? What percentage was this?
 
 bills=c(46, 33, 39, 37, 46, 30, 48, 32, 49, 35 ,30 ,48)
 > sum(bills)
 [1] 557
 > min(bills)
 [1] 30
 > max(bills)
 [1] 49
 > mean(bills)
 [1] 39.78571
 > sum(bills>=40)
 [1] 6
 ((length(bills)-sum(bills>=40))/length(bills))*100
 [1] 57.14286

 
 
 #2.44 You want to buy a used car and find that over 3 months of watching the classifieds you see the following prices
 (suppose the cars are all similar)
 9000 9500 9400 9400 10000 9500 10300 10200
 Use R to find the average value and compare it to Edmund’s (http://www.edmunds.com) estimate of $9500.
 Use R to find the minimum value and the maximum value. Which price would you like to pay?
    
 
 prices=c(9000,9500,9400,9400,10000,9500,10300,10200)
 > mean(prices)
 [1] 9662.5
 > max(prices)
 [1] 10300
 > min(prices)
 [1] 9000
 
 
 
 #2.55 Try to guess the results of these R commands. Remember, the way to access entries in a vector is with [].
 Suppose we assume
 > x = c(1,3,5,7,9)
 > y = c(2,3,5,7,11,13)
 1. x+1
 2. y*2
 3. length(x) and length(y)
 4. x + y
 5. sum(x>5) and sum(x[x>5])
 6. sum(x>5 | x< 3) # read | as 'or', & and 'and'
 7. y[3] 
 8. y[-3] simpleR - Using R for Introductory Statistics
 Univariate Data page 8
 9. y[x] (What is NA?)
 10. y[y>=7]
 
 //////////////////////////////////////////////
 x = c(1,3,5,7,9)
 > y=c(2,3,5,7,11,13)
 > x+1
 [1]  2  4  6  8 10
 > y*2
 [1]  4  6 10 14 22 26
 > length(x)
 [1] 5
 > length(y)
 [1] 6
 > sum(x)
 [1] 25
 > sum(y)
 [1] 41
 > sum(x)+sum(y)
 [1] 66
 > x+y
 [1]  3  6 10 14 20 14
 Warning message:
   In x + y : longer object length is not a multiple of shorter object length
 > sum(x>5)+sum(x[x>5])
 [1] 18
 > y[3]
 [1] 5
 > y[-3]
 [1]  2  3  7 11 13
 > y[x]
 [1]  2  5 11 NA NA
 #Here,NA means that there are no elements present in y for y[11,13].
>y[y>7]
[1] 11 13
 

 
 


#2.6
Use R to compute the following functions. Note, we use X1 to denote the first element of x (which is 0) etc.
1. (X1 + X2 + · · · + X10)/10 (use sum)
2. Find log10(Xi ) for each i. (Use the log function which by default is base e)
3. Find (Xi ??? 4.4)/2.875 for each i. (Do it all at once)
4. Find the difference between the largest and smallest values of x. (This is the range. You can use max and
                                                                      min or guess a built in command.)


x = c(1, 8, 2, 6, 3, 8, 5, 5, 5, 5)
> sum(x[1:10])
[1] 48
> log(x[1:10])
[1] 0.0000000 2.0794415 0.6931472 1.7917595 1.0986123 2.0794415 1.6094379 1.6094379 1.6094379 1.6094379
> x[1:10]-4.4/2.875
[1] -0.5304348  6.4695652  0.4695652  4.4695652  1.4695652  6.4695652  3.4695652  3.4695652  3.4695652  3.4695652
> max(x)-min(y)
[1] 6
 
 
