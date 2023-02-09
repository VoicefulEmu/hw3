Q1: Num eights
Write a recursive function num_eights that takes a positive integer pos and returns the number of times the digit 8 appears in pos.

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function definitions if you so wish.)

  def num_eights(pos):
      """Returns the number of times 8 appears as a digit of pos.

      >>> num_eights(3)
      0
      >>> num_eights(8)
      1
      >>> num_eights(88888888)
      8
      >>> num_eights(2638)
      1
      >>> num_eights(86380)
      2
      >>> num_eights(12345)
      0
      >>> from construct_check import check
      >>> # ban all assignment statements
      >>> check(HW_SOURCE_FILE, 'num_eights',
      ...       ['Assign', 'AnnAssign', 'AugAssign', 'NamedExpr'])
      True
      """
      "*** YOUR CODE HERE ***"
Use Ok to test your code:

python3 ok -q num_eights






Q2: Ping-pong
The ping-pong sequence counts up starting from 1 and is always either counting up or counting down. At element k, the direction switches if k is a multiple of 8 or contains the digit 8.Implement a function pingpong that returns the nth element of the ping-pong sequence without using any assignment statements. (You are allowed to use function definitions.)

You may use the function num_eights, which you defined in the previous question.

Important: Use recursion; the tests will fail if you use any assignment statements. (You can however use function definitions if you so wish.)

Hint: If you're stuck, first try implementing pingpong using assignment statements and a while statement. Then, to convert this into a recursive solution, write a helper function that has a parameter for each variable that changes values in the body of the while loop.

def pingpong(n):
    """Return the nth element of the ping-pong sequence.

    >>> pingpong(8)
    8
    >>> pingpong(10)
    6
    >>> pingpong(15)
    1
    >>> pingpong(21)
    -1
    >>> pingpong(22)
    -2
    >>> pingpong(30)
    -2
    >>> pingpong(68)
    0
    >>> pingpong(69)
    -1
    >>> pingpong(80)
    0
    >>> pingpong(81)
    1
    >>> pingpong(82)
    0
    >>> pingpong(100)
    -6
    >>> from construct_check import check
    >>> # ban assignment statements
    >>> check(HW_SOURCE_FILE, 'pingpong',
    ...       ['Assign', 'AnnAssign', 'AugAssign', 'NamedExpr'])
    True
    """
        "*** YOUR CODE HERE ***"
Use Ok to test your code:

python3 ok -q pingpong
Copy









Q3: Missing Digits
Write the recursive function missing_digits that takes a number n that is sorted in non-decreasing order (for example, 12289 is valid but 15362 and 98764 are not). It returns the number of missing digits in n. A missing digit is a number between the first and last digit of n of a that is not in n.

Important: Use recursion; the tests will fail if you use any loops.

  def missing_digits(n):
    """Given a number a that is in sorted, non-decreasing order,
    return the number of missing digits in n. A missing digit is
    a number between the first and last digit of a that is not in n.
    >>> missing_digits(1248) # 3, 5, 6, 7
    4
    >>> missing_digits(19) # 2, 3, 4, 5, 6, 7, 8
    7
    >>> missing_digits(1122) # No missing numbers
    0
    >>> missing_digits(123456) # No missing numbers
    0
    >>> missing_digits(3558) # 4, 6, 7
    3
    >>> missing_digits(35578) # 4, 6
    2
    >>> missing_digits(12456) # 3
    1
    >>> missing_digits(16789) # 2, 3, 4, 5
    4
    >>> missing_digits(4) # No missing numbers between 4 and 4
    0
    >>> from construct_check import check
    >>> # ban while or for loops
    >>> check(HW_SOURCE_FILE, 'missing_digits', ['While', 'For'])
    True
    """
    "*** YOUR CODE HERE ***"
Use Ok to test your code:

python3 ok -q missing_digits





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

def ascending_coin(coin):
    """Returns the next ascending coin in order.
    >>> ascending_coin(1)
    5
    >>> ascending_coin(5)
    10
    >>> ascending_coin(10)
    25
    >>> ascending_coin(2) # Other values return None
    """
    if coin == 1:
        return 5
    elif coin == 5:
        return 10
    elif coin == 10:
        return 25

def descending_coin(coin):
    """Returns the next descending coin in order.
    >>> descending_coin(25)
    10
    >>> descending_coin(10)
    5
    >>> descending_coin(5)
    1
    >>> descending_coin(2) # Other values return None
    """
    if coin == 25:
        return 10
    elif coin == 10:
        return 5
    elif coin == 5:
        return 1

def count_coins(change):
    """Return the number of ways to make change using coins of value of 1, 5, 10, 25.
    >>> count_coins(15)
    6
    >>> count_coins(10)
    4
    >>> count_coins(20)
    9
    >>> count_coins(100) # How many ways to make change for a dollar?
    242
    >>> count_coins(200)
    1463
    >>> from construct_check import check
    >>> # ban iteration
    >>> check(HW_SOURCE_FILE, 'count_coins', ['While', 'For'])
    True
    """
    "*** YOUR CODE HERE ***"
Use Ok to test your code:

python3 ok -q count_coins
