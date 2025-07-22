Status: 
Tag:
Links: [[200 Data Structures & Algorithms]]

---
> [!note] 
>  # Grokking Patterns



![[Pasted image 20250331203517.png | center]]

This course categorizes coding interview problems into a set of **28 patterns**. Each pattern will be a complete tool - consisting of data structures, algorithms, and analysis techniques - to solve a specific category of problems. The goal is to develop an understanding of the underlying pattern, so that, we can apply that pattern to solve other problems.

## 1. Pattern: Sliding Window

![[Sliding Window.svg | 700 | ]]

**Description:** This pattern involves creating a ‘window’ into the data structure and then moving that window around to gather specific information.

**Usage:** Mostly used in array or list-based problems where you need to find a contiguous subset that fulfills certain conditions.

## 2. Pattern: Two Pointers

![[Pasted image 20240317220933.png]]

Description: This method uses two pointers to traverse an array or a list from different ends or directions.

**Usage:** It’s particularly useful for ordered data structures, where we can make intelligent decisions based on the position of the pointers.


## 3. Pattern: Fast & Slow Pointers

![[220.3 Fast & Slow Pointer Diagram.svg]]


**Description:** In this method, two pointers move at different speeds in a data structure.

**Usage:** It is commonly used to detect cycles in a structure, find middle elements, or to solve other specific problems related to linked lists.


## 4. Pattern: Merge Intervals

![[Pasted image 20250129191151.png]]

**Description:** This pattern involves merging overlapping intervals.

**Usage:** Often used in problems involving time intervals, ranges, or sequences.

## 5. Pattern: Cyclic Sort

![[220.5 Diagram.svg]]

**Description:** This pattern involves sorting an array containing numbers in a given range.

**Usage:** It’s useful in situations where the data involves a finite range of natural numbers.

## 6. Pattern: In-place Reversal of a Linked List

![[Pasted image 20250219181132.png]]

**Description:** This pattern involves reversing elements of a linked list in-place.

**Usage:** It’s generally used when reversing a sequence without using extra space i.e., with a constant space complexity.



---
References: