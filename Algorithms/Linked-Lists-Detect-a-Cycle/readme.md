# [Linked Lists: Detect a Cycle](https://www.hackerrank.com/challenges/ctci-linked-list-cycle)

## Problem Statement

A linked list is said to contain a cycle if any node is visited more than once while traversing the list.

Complete the function provided in the editor below. It has one parameter: a pointer to a Node object named head that points
to the head of a linked list. Your function must return a boolean denoting whether or not there is a cycle in the list. 
If there is a cycle, return true; otherwise, return false.

Note: If the list is empty, head will be null.

## Input Format

Our hidden code checker passes the appropriate argument to your function. You are not responsible for reading any input from stdin.

## Constraints

1 <=list size<= 100

## Output Format

If the list contains a cycle, your function must return true. If the list does not contain a cycle, it must return false. 
The binary integer corresponding to the boolean value returned by your function is printed to stdout by our hidden code checker.

## Solution

### Java
```java
/*
Detect a cycle in a linked list. Note that the head pointer may be 'null' if the list is empty.

A Node is defined as: 
    class Node {
        int data;
        Node next;
    }
*/
boolean hasCycle(Node head) {
    Node fast = head;
    Node slow = head;
    
    while(fast!=null && fast.next!=null){
        slow = slow.next;
        fast = fast.next.next;
        if(fast==slow)
            return true;
    }
    return false;
}
```
