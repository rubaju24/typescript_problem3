# typescript_problem3

ClimbStairs

# Climbing Stairs Problem (Dynamic Programming)

## Overview

This project implements an efficient iterative solution for the **Climbing Stairs Problem** – finding the number of distinct ways to climb to the top of a staircase with n steps, where you can take either 1 step or 2 steps at a time.

## Problem Statement

You are climbing a staircase that has n steps. Each time you can either climb 1 step or 2 steps. In how many distinct ways can you climb to the top?

### Example

For n = 3, there are 3 distinct ways:

- 1 step + 1 step + 1 step
- 1 step + 2 steps
- 2 steps + 1 step

## How It Works

The solution uses the Fibonacci pattern where:

- ways(n) = ways(n-1) + ways(n-2)

This is because to reach step n, you can:

1. Come from step (n-1) by taking 1 step
2. Come from step (n-2) by taking 2 steps

The algorithm iteratively computes the number of ways without recursion:

1. Base cases:
   - n = 0 or 1 → 1 way
   - n = 2 → 2 ways
2. For i from 3 to n:
   - result = first + second (where first = ways(i-2), second = ways(i-1))
   - Update first = second, second = result
3. Return result

## Complexity

- Time: O(n) – single pass from 3 to n
- Space: O(1) – only uses three variables

## Prerequisites

- Node.js (version 12 or higher)
- TypeScript

## Setup and Execution

1. Save the code in a file named climbStairs.ts

2. Install TypeScript:
   npm install -g typescript

3. Compile the file:
   tsc climbStairs.ts

4. Run the compiled file:
   node climbStairs.js

## Usage

const n = 3;
const result = climbStairs(n);
console.log(result); // Output: 3

## Step-by-Step Example

### Example: n = 5

Base cases:
ways(1) = 1
ways(2) = 2

i = 3: ways(3) = ways(2) + ways(1) = 2 + 1 = 3
i = 4: ways(4) = ways(3) + ways(2) = 3 + 2 = 5
i = 5: ways(5) = ways(4) + ways(3) = 5 + 3 = 8

Result = 8

### All ways for n = 4 (5 ways):

1. 1+1+1+1
2. 1+1+2
3. 1+2+1
4. 2+1+1
5. 2+2

## Test Cases

### Test 1: n = 1

Input: 1
Output: 1
Explanation: Only [1]

### Test 2: n = 2

Input: 2
Output: 2
Explanation: [1+1], [2]

### Test 3: n = 3

Input: 3
Output: 3
Explanation: [1+1+1], [1+2], [2+1]

### Test 4: n = 4

Input: 4
Output: 5
Explanation: 1+1+1+1, 1+1+2, 1+2+1, 2+1+1, 2+2

### Test 5: n = 5

Input: 5
Output: 8

### Test 6: n = 6

Input: 6
Output: 13

### Test 7: n = 10

Input: 10
Output: 89

### Test 8: n = 0 (edge case)

Input: 0
Output: 1

## Fibonacci Sequence Pattern

The sequence forms the Fibonacci numbers (shifted):

n: 0 1 2 3 4 5 6 7 8
ways: 1 1 2 3 5 8 13 21 34

## Features

- Optimal O(n) iterative solution
- Constant memory usage (O(1))
- No recursion overhead
- Fast and efficient for large n
- Handles base cases correctly

## Limitations

- Numbers grow exponentially (potential overflow for very large n in some languages)
- In JavaScript, numbers are safe up to n ≈ 79 before hitting MAX_SAFE_INTEGER

## Alternative Approaches

- Recursive solution (exponential time, O(2ⁿ)) – not efficient
- Recursive with memoization (O(n) time, O(n) space)
- Matrix exponentiation (O(log n) time)
- Closed-form formula using golden ratio (O(1) time with floating-point math)

## Mathematical Formula

The number of ways = F(n+1) where F is the Fibonacci sequence:

- F(0) = 0, F(1) = 1
- ways(n) = F(n+1) = (φ^(n+1) - ψ^(n+1)) / √5
- where φ = (1+√5)/2 (golden ratio), ψ = (1-√5)/2

## Variations

- Climb with 1, 2, or 3 steps at a time
- Minimum cost to climb stairs
- Climb with step constraints (e.g., cannot take 2 steps twice in a row)

## Related Problems

- Fibonacci number
- House robber problem
- Decode ways
