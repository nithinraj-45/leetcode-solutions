# Reverse Integer

**LeetCode Problem:** Reverse Integer  
**Difficulty:** Medium  
**Language:** Java  
**Status:** Accepted ✅

## Approach

The goal is to reverse the digits of a given integer.

I used the following logic:

1. Get the last digit using `% 10`.
2. Remove the last digit using `/ 10`.
3. Add the extracted digit to the reversed number.
4. Repeat until the original number becomes `0`.

The main logic is:

`int digit = x % 10;`  
`x = x / 10;`  
`rev = rev * 10 + digit;`

## What I Learned

My initial approach handled the basic reversal logic correctly, but I did not initially consider integer overflow.

In Java, an `int` can store values only within this range:

**-2,147,483,648 to 2,147,483,647**

So before performing:

`rev = rev * 10 + digit;`

I added a condition to check whether the value could go outside the `int` range.

`if (rev > Integer.MAX_VALUE / 10 || rev < Integer.MIN_VALUE / 10)`

If the value can overflow, the solution returns `0`.

This was something I learned after my first attempt failed because I had not considered the integer limit.

## Complexity

- **Time Complexity:** O(log₁₀ n)
- **Space Complexity:** O(1)

## Key Takeaway

This problem helped me understand not only how to reverse an integer using `%` and `/`, but also why checking for integer overflow is important when working with Java `int` values.
