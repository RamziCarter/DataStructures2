
> Recursion
---

Math library 
Math.random()
Math.pow(double a, double b)
Math.max(a,b)
Math.min(a,b)

---

To recur means happen again and again

In computer science, recursion happens when a program calls itself

```Java
  public String aRecurExample(int x, int y)
  {
    return aRecurExample(x-1, y/2, z);
  }  

```

#### Basic Recursion Algorithm 
* If you are already at home. STOP
* Take one step closer to home
* Return to Step 1

Fibbionacci Sequence
* To find the next number you have to add the two previous values
* 4th Fib number is 3rd plus 2nd Fib number
* Fib(n) = fib(n - 1) + fib(n - 2)

When recursion does not stop, we call it an infinite recursion 
That leads to tbe infamous error StackOverflow

Every recursive call requires memory and when recursive calls continue the stack for your program likely runs out of space

__How we make it stop__

* Base Case
  * In the recuring mthod you must check for the smallest case, because there should be no recursion call that time. Often that is ehrn the method is at the end.
  * On essebtial part of recursion, each time the method is called it gets smaller in some way

Finding min recursively

public static int minRecur(int 

---
Palindrom
* A word or phrase that has the same sequence of characters forward ot backwards
  * Kayak
  * Taco Cat
  * Racecar
 
First and last letter are the same
if they are equal keep going inwards

* treat the string as an array of characters

What is the base case?
What is the smallest string that we can check for a palindrome
a single character will always be a palindrome
and empty string of length 0 would also be true

public static boolean isPalindrom(String s)
{
  if(s.length <= 1)
  {
    return true;
  }

  int lastIndex = s.length() - 1;
  
  if(s.charAt(0) != s.charAt(lastIndex))
  {
    return false;
  }

  // remove the first and last elements of the string to create smaller string
  String sub = s.subString(1,lastIndex);

  return isPalindrome(sub);
  
  }
}
---

recursion can provide a solution with very little code
Iterating is a faster option that opening a new stack
Maintaining the recursive calls in the stack can use lots of memory


---

Factorial is a math function where the number is multiplies by all the numbers that came before it

```Java

// base case
if(n ==1)
{
  return 1;
}
return n * factorial(n - 1);
```Java

reversing q string - recursively
To reverse a string recursively uou will need to use the substring method

public static String reverseRec(String input)
{
  if(input.length ==1)
  {
    return input;
  }

  char first = input.charAt(0);
  String afterFirst = input.subString(1);
  String smaller = reverseRec(afterFirst);
  return smaller + first;
}

```

Digits to words write a recursive method that takis in an integer and will print out numeruc wirds for each digit
Example: 321 would print three two one

* base case would be a single digit number must be less than 10
  * print the word from the number
*  
