# leet-day83

# Integer Break

## Problem Description

Given a positive integer `n`, break it into the sum of at least two positive integers and maximize the product of those integers. Return the maximum product you can get.

## Example

### Example 1:

Input: `n = 2`

Output: `1`

Explanation: `2 = 1 + 1, 1 x 1 = 1`

### Example 2:

Input: `n = 10`

Output: `36`

Explanation: `10 = 3 + 3 + 4, 3 x 3 x 4 = 36`

## Constraints

- You may assume that `n` is not less than 2 and not greater than 58.

## Approach

To solve this problem, you can use dynamic programming. Here's a step-by-step explanation of the approach:

1. Handle base cases: If `n` is 2, return 1. If `n` is 3, return 2. These are the base cases, and you need them to compute the maximum product for larger numbers.

2. Create a dynamic programming table, `maxProduct`, of size `n + 1`. Initialize all values to 0. This table will store the maximum products for different values of `n`.

3. Set base cases for numbers 1, 2, and 3. These are used as starting points for computing the maximum product for larger numbers. `maxProduct[1] = 1`, `maxProduct[2] = 2`, and `maxProduct[3] = 3`.

4. Use a loop to fill the dynamic programming table for larger numbers. Start the loop from 4 and go up to `n`.

5. For each number `num`, initialize `maxProductForNum` to 0. This variable will store the maximum product for the current `num`.

6. Use another loop to iterate through smaller numbers from 1 to `num / 2`. For each `subNum`, calculate the product of `maxProduct[subNum]` and `maxProduct[num - subNum]`. Update `maxProductForNum` with the maximum of its current value and this product. This step finds the maximum product for the current `num` by considering all possible ways to break it into two smaller numbers.

7. Update `maxProduct[num]` with the value of `maxProductForNum`, which represents the maximum product for the current `num`.

8. After the loop completes, `maxProduct[n]` will contain the maximum product for the given `n`. Return `maxProduct[n]`.

## Complexity Analysis

The time complexity of this solution is O(n^2) because of the nested loop that iterates through smaller numbers for each `num` from 4 to `n`. The space complexity is O(n) due to the dynamic programming table `maxProduct`.

By following this approach, you can efficiently find the maximum product of integers that sum up to the given `n`.

Y
