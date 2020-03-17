

## 2020 Winter CSS143B Final Exam &nbsp; &nbsp; &nbsp; Student Name:

**All choice questions are single choice**

**1. (2pt) Which of the following statements about sorting algorithm is FALSE?**

- (A) Heap sort has O(1) space complexity
- (B) Quicksort is a stable sorting algorithm
- (C) Bubble sort has O(n^2) time complexity, n square that is
- (D) Merge sort can be implemented by recursion

**2. (2pt) Which of the following statements about Stack and Queue ADT is FALSE?**

- (A) Stack is First-In-Last-Out
- (B) Queue is Last-In-Last-Out
- (C) Stack can be used to implement a recursive algorithm iteratively
- (D) Queue can only be implemented with array so its size is limited by the initial capacity

**3. (2pt) Which of the following statements about software testing is FALSE?**

- (A) JUnit is a Java testing framework
- (B) Testing can be done by comparing actual results from running code with known expcted results  
- (C) Test cases should cover both possible data inputs and code paths
- (D) If my test passes, my code is correct

**4. (2pt) Which of the following statements about the dictionary ADT is FALSE?**

- (A) Chaining can be used to solve the collision problem
- (B) Dictionary always has O(1) time complexity for entry retrieval such as ***get(key)***
- (C) Dictionary can be implemented with array
- (D) The hash function that generates hash key needs to have low complexity (in another word, FAST)



**5. (2pt) Suppose you are using a Github repository for one of the dreadful homeworks. You have been working on you laptop with a clone of that repo. On the day before the due date the laptop decides that it won't start at all. Realizing that you happen to have another laptop available, describe how you would recover your work onto it from Github and continue to finish the homework on time. List specific git commands you would use.**

```bash



```

**6. (10pt) You can't handle the truth!**

In the lecture we saw the following code that calculate and sort the word frequency based on part of the movie "a few good men".

```java
        // use map to count the occurrences of each word
        HashMap<String, Integer> wordMap = new HashMap<>();
        for (String word : words) {
            if (wordMap.containsKey(word)) {
                wordMap.put(word, wordMap.get(word)+1);
                continue;
            }
            wordMap.put(word, 1);
        }

        // sort the map based on number of occurrences
	// 2nd block starts here
        TreeMap<Integer, Set<String>> sortedMap = new TreeMap<>(Collections.reverseOrder());
        for (Map.Entry<String, Integer> entry : wordMap.entrySet()) {
            int key = entry.getValue();
            Set<String> values = sortedMap.containsKey(key) ? 
                       sortedMap.get(key) : new HashSet<>();
            values.add(entry.getKey());
            sortedMap.put(entry.getValue(), values);
        }
```

Answer the following question about this code:

6.1 (2pt) Explain why the entry value of the variable ***sortedMap*** is a Set instead of a String.

```bash




```

6.2 (3pt) Why is ***sortedMap*** defined as a TreeMap instead of HashMap? 

```bash



```

6.3 (3pt) Suppose ***wordMap*** has the following data:

```bash
and : 8
men : 1
of : 3
what : 2
we : 3
```

What is the corresponding data in ***sortedMap*** after running the given code?

```bash



```

6.4 (2pt) Analyze and produce the time complexity for the code that generates data into ***sortedMap***. It's the 2nd block of the given code. Note that this involves accessing the wordMap and inserting data into the ***sortedMap***, which is of type ***TreeMap***. The result will be in terms of number of word ***n***.

```bash



```

**7. (5pt) Improve the following code for better code quality?**

```java
        Stack<Integer> test1 = new Stack<Integer>();
        test1.push(-1);
        tests.add(test1);
        Stack<Integer> test2 = new Stack<Integer>();
        test2.push(0);
        tests.add(test2);
        Stack<Integer> test3 = new Stack<Integer>();
        test3.push(1);
        test3.push(0);
        tests.add(test3);
        Stack<Integer> test4 = new Stack<Integer>();
        test4.push(2);
        test4.push(1);
        test4.push(0);
        tests.add(test4);
        Stack<Integer> test5 = new Stack<Integer>();
        test5.push(5);
        test5.push(1);
        test5.push(3);
        test5.push(2);
        tests.add(test5);
```

Please list the problem of the above code in terms of code quality and then provide the improved code

```bash



```


**8. (5pt) Heap can be used to implement a priority queue. However, when the items in the priority queue has the same priority, dequeue() should fall back to the FIFO rule like regular queue, which heap cannot guarentee. Describe your design to solve this problem.**

```bash



```

**9. (20pt) Based on the following tree**

```bash
          41
        /    \
       18    33
      / \    / \
     11  3  1  19 
    /
   5
```

9.1 (15pt) What is the pre-order, in-order and post-order traversal of the above tree
```bash
pre-order:



In-order:



post-order:

```

9.2 (5pt) This tree also happens to be a bianry heap tree. Write down how this tree can be stored as a heap using an array

```bash



```



**10. (20pt) Write the code to iteratively reverse THE SECOND HALF of a single linked list in place.**

The single linked list has a dummy node. And "second half" means from the middle of the list to the end. If there's odd number of nodes, the node in the dead center does not participate in the reversal. The dummy node is not considered part of the list to be counted for reversal.

10.1 (15pt) Write the code given the following list node definition

   ```java
   public class ListNode {
       int val;
       ListNode next;
       public ListNode(int val) {
           this.val = val;
           this.next = null;
       }
   }
   ```

For example, 

```bash
Input: h-->1-->3-->2, output: h-->1-->3-->2
Input: h-->1-->5-->3-->4, output: h-->1-->5-->4-->3
Input: h-->1-->2-->3-->4-->5, output: h-->1-->2-->3-->5-->4
Input: h-->1-->2-->3-->4-->5-->6, output: h-->1-->2-->3-->6-->5-->4
```

The reversal is to be done **in place** like the regular iterative reversal.

```java
public class Solution {
      public void reverse2ndHalf(ListNode head) {
      // your code here
      // head is the dummy node
    }
}
```



10.2 (5pt) What's the time complexity of your code in big O notation ?

```bash



```



**11. (10pt) Answer the following questions about the Cats and animal classes**

```java
public abstract class Animal {
    private String name;
    private String gender;
    private int age;
    
    public abstract void speak();
    
    public Animal(String name, String gender, int age) {
        this.name = name;
        this.gender = gender;
        this.age = age;
    }
    
    public String getName() {
        return name;
    }
}

public class Cat extends Animal {
  private String furColor;
  public Cat(String name, String gender, int age, String furColor) {
        super(name, gender, age);
        this.furColor = furColor;
    }
    
    @Override
    public void speak() {
        System.out.println("Cat " + getName() + " says 'meow'");
    }
}
```

11.1 (2pt) Why does the keyword ***abstract*** do in the definition of ***speak()***  in Animal class?

```bash


```

11.2 (2pt) What does ***"@Override"*** mean?

```bash


```

11.3 (2pt) What does the call to ***super(name, gender, age)*** do?

```bash

```

11.4 (2pt) The ***Animal*** class is defined as an abstract class. But Java also has ***interface*** type. What's the difference between an abstract class and interface in Java?

```bash


```

11.5 (2pt) What is the output of the following code?

```java
Animal animal;
animal = new Cat("coco", "he", 13, "black");
animal.speak();
```

```bash


```



**12. (20pt) Write the code to check if two binary trees are identical**

Hint: go recursively.

A binary tree node is defined as the following:

 ```java
 public class TreeNode {
     int val;
     TreeNode left;
     TreeNode right;
     TreeNode(int x) { val = x; }
 }
 ```

12.1 (10pt) Write your solution in 

```java
class Solution {
    public boolean isIdentical(TreeNode tree1, TreeNode tree2) {
      // your code here
    }
}
```

***isIdentical*** returns true is both trees are identical (same shape, same node values in all the nodes). False otherwise. For example

```bash
Input:     3         3
          / \       / \
         8   1     8   1
Output: true

Input:     3         3
          /         / \
         8         8   1
Output: false

Input:     3         3
          / \       / \
         1   8     8   1
Output: false

Input:     3         2
          / \       / \
         1   8     1   8
Output: false
```

An empty tree is identical to an empty tree.

12.2 (10pt) Write a test plan for your code. List your proposed test cases with specific binary tree inputs. No need to write actual code.

```bash




```

**(10pt) Bonus Points 1**

For the "unique path" problem we dicussed in lecture, the following recursion solution was given

```java
    public static int uniquePaths(int m, int n) {
        if (m==0 || n==0) {
            return 0;
        }
        if (m==1 && n==1) {
            return 1;
        }
        return uniquePaths(m-1, n) + uniquePaths(m, n-1);
    }
```

This implementation has bad performance because of the "repeated subprobem". Re-write this with an iterative solution that trades (uses) space for better time performance.  

```java
    public static int uniquePathsIterative(int m, int n) {
			// your code here
    }
```

Discuss the big O time complexity of this iterative method.

```bash




```

**(5pt) Bonus Points 2**

In the first lecture we saw a cool lego truck. What problem was it used for illustration?
