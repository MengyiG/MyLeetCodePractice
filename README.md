# Cracking the Leetcode Problems 🥳

This is a blog that tracks my leetcode learning path. Each day, I post the below contents:

- what I have learned from [代码随想录](https://programmercarl.com/%E6%95%B0%E7%BB%84%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html) and useful links 今日学习的文章链接和视频链接
- my thoughts on the problems 自己看到题目的第一想法
- my thoughts after the learning 看完代码随想录之后的想法
- difficulties 自己实现过程中遇到哪些困难
- others 今日收获，记录一下自己的学习时长

## DAY 1: Binary Search & Remove Elements

- [x] Problem 704
  - [ ] Problem 35, easy
  - think about when to use break;
  - when to find the target, try to get the left and right edges.
  - [ ] Problem 34, medium
  - [ ] Problem 69, easy
  - [ ] Problem 367, easy
- [x] Problem 27

  - [x] Problem 26, easy
  - [x] Problem 283, easy
  - [ ] Problem 844, easy
  - [ ] Problem 977, easy

- what I have learned & useful links
  - [binary search](https://programmercarl.com/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.html) & [video](https://www.bilibili.com/video/BV1fA4y1o715/)
  - [remove element](https://programmercarl.com/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.html) & [video](https://www.bilibili.com/video/BV12A4y1Z7LP/?spm_id_from=333.788&vd_source=d216e0483cb2bc8d1140b35f1674e41d)
- thoughts:
  - 704
    - to identify if the search range if valid or not, we can try to use a value to test, for example, in a while loop, to check if we should use [left, right] or [left, right), we can try to test if it makes senses when left == right.
    - to decide how to move the pointer, i.e, whether left = middle or left = middle +1, we need to go back to chcek the condition. If the condition is if(nums[middle] > target) and if the range is [left, right], it means that middle is definitely not the value that we are looking for, then in this case, we should move to middle+1. In a word, do not duplicate the searching range. However, if the range is [left, right), it means that the next searching range is not including the right pointer, so right = middle or left = middle+1.
  - 27 -> 2 pointers
    - Initialize index to 0, which represents the current position for the next non-target element.
    - Iterate through each element of the input array using the i pointer.
    - For each element nums[i], check if it is equal to the target value.
      - If nums[i] is not equal to val, it means it is a non-target element.
      - Set nums[index] to nums[i] to store the non-target element at the current index position.
      - Increment index by 1 to move to the next position for the next non-target element.
    - Continue this process until all elements in the array have been processed.
    - Finally, return the value of index, which represents the length of the modified array.
  - difficulties
    - how to define the ranges.
    - how to remove the duplicates in-place.
  - others
    - integer overflow:
      int left = Integer.MAX_VALUE - 2; // Maximum value of int - 2
      int right = Integer.MAX_VALUE; // Maximum value of int
      int mid = left + ((right - left) / 2);
      System.out.println(mid); // Output: 2147483647
      so use **int mid = left+((right-left)/2);** instead of mid = (left+right)/2

## Highlights

Data Structures, Binary Search, Two Pointers,

![Mengyi Cartoon Pic](/Live,%20Love,%20Learn.png)

Know more about **me** by

- 🙋🏻‍♀️ going to my [Website](https://mengyig.github.io/#)
- 😁 visiting my [LinkedIn](https://www.linkedin.com/in/mengyi-guo/)
- 🎥 checking my [Youtube](https://www.youtube.com/channel/UCu7Q8pfeEvjgTxVyj7YVxHw)
