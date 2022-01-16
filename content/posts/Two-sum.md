---
title: "Two Sum"
date: 2022-01-16T14:50:46-05:00
draft: false
categories: 
    - Algorithm
    - LeetCode
    - HashMap
cover:
    image: /images/postImages/algorithms/algorithms.jpg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "<alt text>"
    caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---

Hey guys,   

I am going to start posting the solutions for some of the coding exercise I am solving through [Leetcode](https://leetcode.com/). If you are preparing for the tech interviews, I would definitely reccommend this resource.  

It may seems intimidating first, but start with the easy problems. If you get stuck on particular problem, then see the solution and understand the approach/pattern in it and then try to solve it yourself again from your understanding. This being said, let's tackle our first problem.  

## Problem statement  

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

&nbsp;  

```
Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]

Constraints:  

* 2 <= nums.length <= 104
* -109 <= nums[i] <= 109
* -109 <= target <= 109
* Only one valid answer exists.
```
&nbsp;  

From reading this question, your first intuition might be using a nested for loops and find a pair which yield the target sum. Although, this is valid solution, it is not quite efficient. This approach results in O(n<sup>2</sup>) solution.  

There is a better way to solve this. We can utilize the HashMap/dictionary. 

## Solution explanation

We will first initiate an empty hash map. Then we will start looping over the values one by one. Suppose if we take the first example as reference, for given array [2,7,11,15], we will take the value 2. Now to find the value such that by suuming it with 2 gives us the target value 9. The logic looks something like this, `target = 2 + x`.
So basically we are looking for value `target - 2 = x` which is 7.  

chekc if the value 7 exist in the hash map, if not then we will add 2 along with it's index 0. Repeat this same step for the next number 7. For 7, we are looking for value `9 - 7` which is `2`. Now check in our hash map if the key `2` exist. Yes it does!!! so we will return the current value(7)'s index and 2's index in the array. The return value will be `[0,1]`

Using this approach, we will loop over the array only once, so the time complexity is O(n). We are also using the hashmap to store the values we encounter, so the space complexity is O(n) as well.  

## Solution Code

&nbsp;  

```python
def twoSum(nums, target):
    values = {}
    for i, n in enumerate(nums):
        if(target-n in values):
            return[values[target-n],i]
        values[n] = i
    return
```

&nbsp;  

Now ask your self a question, suppose the given array is sorted, will it change the method we use to solve this ? or is there any better way ?? 
There is a better way. I will discuss about it in the next post.  





