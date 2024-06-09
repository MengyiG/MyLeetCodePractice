# Cracking the Leetcode Problems 🥳

This is a blog that tracks my leetcode learning path. Each day, I try to include the below contents:

- the problems that I practice 相关的题型以及拓展题目
- what I have learned from [代码随想录](https://programmercarl.com/%E6%95%B0%E7%BB%84%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html) and useful links 学习的文章链接和视频链接
- my thoughts on the problems or after the learning 自己看到题目的第一想法和看完代码随想录之后的想法
- difficulties 自己实现过程中遇到哪些困难
- others 今日收获，记录一下自己的学习时长

## D-1: Array 01

- [x] Problem 704. **Binary Search**
  - [x] Problem 35
  - [ ] Problem 34, medium
  - [ ] Problem 69
  - [ ] Problem 367
- [x] Problem 27. **Remove Element**

  - [x] Problem 26
  - [ ] Problem 283
    - swap while keeping track of the 2 pointers.
  - [ ] Problem 844
  - [ ] Problem 977

### useful links & thoughts

- [array](https://programmercarl.com/%E6%95%B0%E7%BB%84%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html)
- 🔎 [704](https://programmercarl.com/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.html) - to identify if the search range if valid or not, we can try to use a value to test, for example, in a while loop, to check if we should use [left, right] or [left, right), we could try to test if it makes senses when left == right.
  - to decide how to move the pointer, i.e, whether left = middle or left = middle +1, we need to go back to chcek the condition. If the condition is if(nums[middle] > target) and if the range is [left, right], it means that middle is definitely not the value that we are looking for, then in this case, we should move to middle+1. In a word, do not duplicate the searching range. However, if the range is [left, right), it means that the next searching range is not including the right pointer, so right = middle or left = middle+1.
- 🗑️ [27](https://programmercarl.com/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.html) - use slow and fast pointers.
  - Initialize index to 0, which represents the current position for the next non-target element.
  - Iterate through each element of the input array using the i pointer.
  - For each element nums[i], check if it is equal to the target value.
    - If nums[i] is not equal to val, it means it is a non-target element.
    - Set nums[index] to nums[i] to store the non-target element at the current index position.
    - Increment index by 1 to move to the next position for the next non-target element.
  - Continue this process until all elements in the array have been processed.
  - Finally, return the value of index, which represents the length of the modified array.

### difficulties

- how to define the ranges.
- how to remove the duplicates **in-place** -> use slow and fast pointers.

### others

- integer overflow:
  int left = Integer.MAX_VALUE - 2; // Maximum value of int - 2
  int right = Integer.MAX_VALUE; // Maximum value of int
  int mid = left + ((right - left) / 2);
  System.out.println(mid); // Output: 2147483647
  so use **int mid = left+((right-left)/2);** instead of mid = (left+right)/2
- relate sorted array (with non-duplicated values) to binary search.

## D-2: Array 02

- [x] Problem 977. **Squares of a Sorted Array**
  - [x] Problem 88 (be aware when the condition that nums2.length is greater than nums1)
- [x] Problem 209, medium. **Minimum Size Subarray Sum**
  - [ ] Problem 904, medium
  - [ ] Problem 76, hard
- [x] Problem 59, medium. **Spiral Matrix II**

  - [ ] Problem 54, medium
  - [ ] Problem 146, medium

### useful links & thoughts

- 🙌 [977](https://programmercarl.com/0977.%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E7%9A%84%E5%B9%B3%E6%96%B9.html) - find an O(n) solution. Use 2 pointers. The smallest value should be somewhere in the middle unless it's in the leftmost. Therefore, try to compare the 2 edges and put it with index i, after which the relative pointer should increase or decrease.
- 🛝 [209](https://programmercarl.com/0209.%E9%95%BF%E5%BA%A6%E6%9C%80%E5%B0%8F%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84.html) - To dfine a sliding window, we need to think about
  - what is within the window
  - how to move the start pointer
  - how to move the end pointer
  - think whether use while or if conditions.
- 🌀 [59](https://programmercarl.com/0059.%E8%9E%BA%E6%97%8B%E7%9F%A9%E9%98%B5II.html#%E7%AE%97%E6%B3%95%E5%85%AC%E5%BC%80%E8%AF%BE)
  - deal with the ranges: [left, right). It means that during each spiral(loop), we add the first element while leave the last element to next loop.
  - find out how many rounds we move -> n/2 if n is even and consider n is odd as well.
  - use offeset to find out the elements within the spiral.

### difficulties

- how to define a sliding window with correct start and end pointers.
- in problem 59, the i and j pointer will be changing during each iteration. Therefore, please be aware of starter pointer and how to iterate within the for loop.

## D-3: Linked List 01

- [x] Problem 203. **Remove Linked List Elements**
- [x] Problem 707. **Design Linked List**
- [x] Problem 206. **Reverse Linked List**

### useful links & thoughts

- [LinkedList](https://programmercarl.com/%E9%93%BE%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html)
- 🖇️ [977](https://programmercarl.com/0977.%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E7%9A%84%E5%B9%B3%E6%96%B9.html)
- 👀 [707](https://programmercarl.com/0707.%E8%AE%BE%E8%AE%A1%E9%93%BE%E8%A1%A8.html)
- ◀️ [206](https://programmercarl.com/0206.%E7%BF%BB%E8%BD%AC%E9%93%BE%E8%A1%A8.html)

### difficulties

### others

## D-4: Linked List 02

- [x] Problem 24. **Swap Nodes in Pairs**
- [x] Problem 19. **Remove Nth Node From End of List**
- [ ] Problem 160. **Intersection of Two Linked Lists**
- [x] Problem 142. **Linked List Cycle II**

### useful links & thoughts

- [24](https://programmercarl.com/0024.%E4%B8%A4%E4%B8%A4%E4%BA%A4%E6%8D%A2%E9%93%BE%E8%A1%A8%E4%B8%AD%E7%9A%84%E8%8A%82%E7%82%B9.html)
- [19](https://programmercarl.com/0019.%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E5%80%92%E6%95%B0%E7%AC%ACN%E4%B8%AA%E8%8A%82%E7%82%B9.html)
- [160](https://programmercarl.com/%E9%9D%A2%E8%AF%95%E9%A2%9802.07.%E9%93%BE%E8%A1%A8%E7%9B%B8%E4%BA%A4.html)
- [142](https://programmercarl.com/0142.%E7%8E%AF%E5%BD%A2%E9%93%BE%E8%A1%A8II.html)

### difficulties

### others

---

![Mengyi Cartoon Pic](/Live,%20Love,%20Learn.png)

Know more about **me** by

- 🙋🏻‍♀️ going to my [Website](https://mengyig.github.io/#)
- 😁 visiting my [LinkedIn](https://www.linkedin.com/in/mengyi-guo/)
- 🎥 checking my [Youtube](https://www.youtube.com/channel/UCu7Q8pfeEvjgTxVyj7YVxHw)
