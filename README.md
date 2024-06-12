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
- 🖇️ [977](https://programmercarl.com/0977.%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E7%9A%84%E5%B9%B3%E6%96%B9.html) - 2 solutions. One is to work with the original linked list while the other is to set up a dummy node.
- 👀 [707](https://programmercarl.com/0707.%E8%AE%BE%E8%AE%A1%E9%93%BE%E8%A1%A8.html) - I got a pretty difficult time trying to figure out how to addAtIndex. It turned out that the pointer was set to the wrong place.
- ◀️ [206](https://programmercarl.com/0206.%E7%BF%BB%E8%BD%AC%E9%93%BE%E8%A1%A8.html) - use 2 pointers. The key is to keep a temp pointer that holds the next node, after which to move both the pre and cur pointer; Another solution is to recursively call the mothods.

### difficulties

- The most challenging for Linked List is to understand node and its pointer. Linked List forms a series of connected nodes, where each node stores the data and the address of the next node.
- When working with Linked List problems, always think if the very first node should be separated dealth with.
- Unlike arrays, linked lists do not allow direct access to elements by index. Traversal is required to reach a specific node.

### others

- Extra Memory: Linked lists require additional memory for storing the pointers, compared to arrays.

## D-4: Linked List 02

- [x] Problem 24. **Swap Nodes in Pairs**
- [x] Problem 19. **Remove Nth Node From End of List**
- [x] Problem 160. **Intersection of Two Linked Lists**
- [x] Problem 142. **Linked List Cycle II**

### useful links & thoughts

- [24](https://programmercarl.com/0024.%E4%B8%A4%E4%B8%A4%E4%BA%A4%E6%8D%A2%E9%93%BE%E8%A1%A8%E4%B8%AD%E7%9A%84%E8%8A%82%E7%82%B9.html)
- [19](https://programmercarl.com/0019.%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E5%80%92%E6%95%B0%E7%AC%ACN%E4%B8%AA%E8%8A%82%E7%82%B9.html)
- [160](https://programmercarl.com/%E9%9D%A2%E8%AF%95%E9%A2%9802.07.%E9%93%BE%E8%A1%A8%E7%9B%B8%E4%BA%A4.html)
- [142](https://programmercarl.com/0142.%E7%8E%AF%E5%BD%A2%E9%93%BE%E8%A1%A8II.html)

### difficulties

### others

## D-6: Hash Table 01

- [x] Problem 242. **Valid Anagram**
  - [ ] Problem 383
  - [ ] Problem 49
  - [ ] Problem 438
- [x] Problem 349. **Intersection of Two Arrays**
  - [ ] Problem 350
- [x] Problem 202. **Happy Numbers**
- [x] Problem 1. **Two Sum**

### useful links & thoughts

- [Hash Table](https://programmercarl.com/%E5%93%88%E5%B8%8C%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html)
  - Hash Collision Techniques.
- 👩🏻‍💻 [242](https://programmercarl.com/0242.%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.html)
  - This is quite easy. We just need iterate the two strings and use hash table to keep track of the frequency of the letters. Then, we can just check if the frequency is zero.
- ⚔️ [349](https://programmercarl.com/0349.%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86.html)
  - HashSet sacrifices space for time.
  - Hash Table(array) is another option. (on the condition that the numbers are limited.)
  - Be aware when transforming the result ArrayList or set to array. (resSet.stream().mapToInt(x -> x).toArray();)
- 😃 [202](https://programmercarl.com/0202.%E5%BF%AB%E4%B9%90%E6%95%B0.html)
  - Use a private method to get the new number and use set to check if the sum is duplicated.
- 2️⃣ [1](https://programmercarl.com/0001.%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C.html)
  - Think of a running hashmap.

### difficulties

- Use % to get the digits of a number in problem 202. Get ones first and use /10 to get the next digit.

### others

## D-7: Hash Table 02

- [x] Problem 454. medium **4Sum II**
- [x] Problem 383. **Ransom Note**
- [x] Problem 15. medium **3Sum**
- [x] Problem 18. medium **4Sum**

### useful links & thoughts

- 4️⃣ [454](https://programmercarl.com/0454.%E5%9B%9B%E6%95%B0%E7%9B%B8%E5%8A%A0II.html) - it asked to return the number of tuples and all nums are of length n, which makes it easier. Use 2 hash maps. One hashmap is to iterate nums1 and nums2 to get the sum and the other to get the sum of nums3 and nums3. Check if the sum of nums3 and nums4 exist in the map, if yes, then we can add to the res.
- 📒 [383](https://programmercarl.com/0383.%E8%B5%8E%E9%87%91%E4%BF%A1.html) - easy one, use hash table to iterate the 2 strings and check if any element of this hash table is below zero.
- 3️⃣ [15](https://programmercarl.com/0015.%E4%B8%89%E6%95%B0%E4%B9%8B%E5%92%8C.html)
  - sort by Arrays.sort()
  - rule out the condition when the first few elements <= 0 as the smallest element should be greater than zero. Be aware when i == 0.
  - use twoSum to get the result.
  - in twoSum, use 2 pointers. The left pointer should be i+1, and right pointer should be nums.length-1. Pay attention to the condition the indexes should not be duplicated.
- ➕ [18](https://programmercarl.com/0018.%E5%9B%9B%E6%95%B0%E4%B9%8B%E5%92%8C.html)- similar to problem 15. Also need to rule out the condition when nums[i]>0 && nums[i] > target, and when i > 0 && nums[i - 1] == nums[i]. This is to reinforce problem 15 solutions.

### difficulties

- in problem 15 and 18, the question to remove duplicate indices are tricky. If we use
  ```java
  if (i > 0 && nums[i] == nums[i - 1]) {
      continue;
  }
  ```
  then, we are judging if the current element is the same as the previous one. In nums={-1, -1 ,2}, the code works. However, if I use,
  ```java
  if (nums[i] == nums[i + 1]) {
  continue;
  }
  ```
  then, nums={-1, -1 ,2}, would be ruled out, which is not corrent.
- how to remove the second and third duplicated results:

  ```java
    while (right > left && nums[right] == nums[right - 1]) right--;
    while (right > left && nums[left] == nums[left + 1]) left++;
  ```

### others

- when adding integers, be aware of the potential overflow. By casting to long, you ensure that the intermediate sum can accommodate larger values:

  correct:

  ```java
  long sum = (long) nums[i] + nums[j] + nums[left] + nums[right];
  ```

  ```java
  // Incorrect: This might still overflow before casting to long
  long sum = (long) (nums[i] + nums[j] + nums[left] + nums[right]);
  ```

  casting each element to long before summing them, rather than casting the sum after adding the int values, ensures that the addition is performed using long arithmetic. If you don't cast before adding, you risk overflow during the addition.

## D-8: String 01

- [x] Problem 344. **Reverse String**
- [x] Problem 541. **Reverse String II**
- [x] Problem 54. **替换数字** from [KamaCoder](https://kamacoder.com/problempage.php?pid=1064)

### useful links & thoughts

- 🔄 [344](https://programmercarl.com/0344.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.html) - use 2 pointers or bitwise operators.
- ↩️ [541](https://programmercarl.com/0541.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2II.html) - Similar to problem 344, the tricky part is to
  - deal with the rest k elements. (think about Math.min to get the end pointers or check if i+k <= ch.length).
  - how to increment index.
- ⊹ [54](https://kamacoder.com/problempage.php?pid=1064)
  - get the number of digits: count
  - create new array by s.length()+5\*count.
  - copy the original array to the newly created array:
    ```java
    System.arraycopy(s.toCharArray(), 0, newS, 0, sOldSize);
    ```
  - replace from the last char of the new array. If not digit, keep it; otherwise, use index to get the letter:
    ```java
    newS[i] = 'r';
    newS[i - 1] = 'e';
    newS[i - 2] = 'b';
    newS[i - 3] = 'm';
    newS[i - 4] = 'u';
    newS[i - 5] = 'n';
    i -= 5;
    ```

### difficulties

### others

- bitwise XOR (exclusive OR) operator:
  - If the corresponding bits are the same (both 0 or both 1), the result bit is 0.
  - If the corresponding bits are different (one is 0 and the other is 1), the result bit is 1.
    we can use this operator when
  - swapping Two Numbers Without a Temporary Variable.
  - flipping bits.

## D-9:

- [x] Problem . **..**

### useful links & thoughts

- [..]()

### difficulties

### others

---

![Mengyi Cartoon Pic](/Live,%20Love,%20Learn.png)

Know more about **me** by

- 🙋🏻‍♀️ going to my [Website](https://mengyig.github.io/#)
- 😁 visiting my [LinkedIn](https://www.linkedin.com/in/mengyi-guo/)
- 🎥 checking my [Youtube](https://www.youtube.com/channel/UCu7Q8pfeEvjgTxVyj7YVxHw)

```

```
