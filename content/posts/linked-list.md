---
title: "Linked List"
date: 2022-01-08T10:14:42-05:00
draft: true
categories: 
    - Data-structures
cover:
    image: /images/postImages/linkedList/1.jpg#center
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "<alt text>"
    caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---

## Overview

So you might be wondering, what is this Linked List data structure is ? I will try to explain it in easy to understand fashion.

You must be already familiar with the term ‘data structure’. Data structure are how we store the data. In most modern programming languages, some data structures come in-built. For example, array or hash map etc. We need to decide which data structure we need to use as per our use case. 

In certain situation, we need to store complex data in our program to efficiently store and retrieve it. Take an example of how the Facebook might be storing their user data ? Or how banking system keep track of all the account holder and their transactions. In these cases, simple data-structures, like array, will not suffice. We need to develop our own data-structure for this purpose using primitive data-types and structures. 

## Structure of linked list

Linked list are kind of similar to array in the sense that they are also a linear data-structure. But unlike array, linked list is dynamic, means you can shrink and grow the size of the structure. The data store in linked list are not stored next to each other, but randomly scattered through the memory.  You might wonder, well then you how does each data point knows about the next data. I will start with a simple linked list to explain this. There are several other types of linked list, but I will discuss them in a separate post.

The linked list store the data in form of Node(not Node.js. duh!!). A Node is a custom data structure that can store a value and the address of the next Node.

&nbsp;  


```javascript

Class Node {
  constructor(value) {
    this.value = value
    this.next = null
  }
}

// Instanciate the Node object:
let node1 = new Node(“Hello”)
```
&nbsp;  

The starting point of the list is a reference to the first node, which is referred to as the head. Nearly all linked lists must have a head, because this is effectively the only entry point to the list and all of its elements, and without it, you wouldn’t know where to start! The end of the list isn’t a node, but rather a node that points to null, or an empty value. 

&nbsp;  

![linked-list](/images/postImages/linkedList/2.png#center)

&nbsp;  

## Implementing a linked list.


Without knowing much about the linked list, we can implement linked list like considering simple explanation I mentioned above.

&nbsp;  

```javascript

Class Node {
  constructor(value) {
    this.value = value
    this.next = null
  }
}

// Instanciate the Node object:
let node1 = new Node(“Hello”)

node1.next = new Node(“How”)
node1.next.next = new Node(“are”)
node1.next.next.next = new Node(“you)

```
&nbsp;  

The above method gets quite tedious after a while, so we create a separate Linked List class that utilize the existing Node class to store the data and has some method that we can use to operate on data like add new Node, remove Node, search particular value and so on. Let’s try to implement the linked list structure from this.

&nbsp;  

```javascript
Class SinglyLinkedList {
  constructor() {
    this.head = null
    this.tail = null
    this.length = 0
  }
}
```
&nbsp;  

That’s it! It is not so hard as you might have you, right?? Now, as I mentioned before, we need some methods to operate on the data. Currently, we do not have any method in this newly created linked list structure to add the data. Let’s create a method called ‘push’ to link/add the node with each other.

&nbsp;  

```javascript
// … linked list constructor as above

push(value) {
newNode = new Node(value)
	/* check if the node exist at the head, if not then add new Node at the head position
	And if the nodes already exist in the linked list then add new node add tail position */
    if(!this.head) {
      This.head = newNode
  } else {
    This.tail.next = newNode
    This.tail = newNode
  } 
}
```
&nbsp;  

We can define several other methods for the linked list structure like searching for value, adding value at the beginning, removing particular value etc. 

As we have seen, that linked list store values dynamically in memory, and it is linear structure where each node is connected to another node in linear fashion, so what is the advantage of using linked list compare to an array ?? 

## Use cases of linked list

Think if you were to add the element at the beginning of an array, what would happen ? All the elements in the array need to shift in order to create a place at the beginning. This is operation is O(n). In contrast with linked list, we can add the element/Node at the beginning or at the head position and simply modify the pointer of head and new Node, which requires O(1) time complexity. On the other hand, linked list are not as efficient in searching as array. 

Imagine searching for the value in a linked list, You need to traverse the elements one by one to find the value. This is O(n) time complexity. There is no scratching the value with index in linked list since elements are stored randomly in memory. If you ever find yourself having to do something that requires a lot of traversals, iteration, or quick index-level access, a linked list could be your worst enemy. However, if you want to add a bunch of elements to a list and aren’t worried about finding elements again later, or if you know that you won’t need to traverse through the entirety of the list often, a linked list could be a good option.

Hopefully this article gave you primary explanation of the linked list. So far, we have only seen the singly linked list, which is most the simplest form of linked list. I am planning to write another post that explain various other linked list types like doubly linked list, circular linked list etc. 

