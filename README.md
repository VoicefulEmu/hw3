Q1: Num eights

Write a recursive function num_eights that takes a positive integer pos and returns the number of times the digit 8 appears in pos.

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function definitions if you so wish.)






Q2: Ping-pong
The ping-pong sequence counts up starting from 1 and is always either counting up or counting down. At element k, the direction switches if k is a multiple of 8 or contains the digit 8.Implement a function pingpong that returns the nth element of the ping-pong sequence without using any assignment statements. (You are allowed to use function definitions.)

You may use the function num_eights, which you defined in the previous question.

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function definitions if you so wish.)

Hint: If you're stuck, first try implementing pingpong using assignment statements and a while statement. Then, to convert this into a recursive solution, write a helper function that has a parameter for each variable that changes values in the body of the while loop.





Q3: Missing Digits
Write the recursive function missing_digits that takes a number n that is sorted in non-decreasing order (for example, 12289 is valid but 15362 and 98764 are not). It returns the number of missing digits in n. A missing digit is a number between the first and last digit of n of a that is not in n.

Important: Use recursion; the tests will fail if you use any loops.



Q4: Count coins
Given a positive integer change, a set of coins makes change for change if the sum of the values of the coins is change. Here we will use standard US Coin values: 1, 5, 10, 25. For example, the following sets make change for 15:

15 1-cent coins
10 1-cent, 1 5-cent coins
5 1-cent, 2 5-cent coins
5 1-cent, 1 10-cent coins
3 5-cent coins
1 5-cent, 1 10-cent coin

Thus, there are 6 ways to make change for 15. Write a recursive function count_coins that takes a positive integer change and returns the number of ways to make change for change using coins.

You can use either of the functions given to you:

ascending_coin will return the next larger coin denomination from the input, i.e. ascending_coin(5) is 10.
descending_coin will return the next smaller coin denomination from the input, i.e. descending_coin(5) is 1.
There are two main ways in which you can approach this problem. One way uses ascending_coin, and another uses descending_coin.

Important: Use recursion; the tests will fail if you use loops.

Hint: Refer the implementation of count_partitions for an example of how to count the ways to sum up to a final value with smaller parts. If you need to keep track of more than one value across recursive calls, consider writing a helper function.
