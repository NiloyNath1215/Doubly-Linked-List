# Doubly-Linked-List

A Doubly Linked List (DLL) contains an extra pointer, typically called the previous pointer, together with the next pointer and data which are there in the singly linked list.

# Advantages of DLL over the singly linked list:

A DLL can be traversed in both forward and backward directions. 
The delete operation in DLL is more efficient if a pointer to the node to be deleted is given. 
We can quickly insert a new node before a given node. 
In a singly linked list, to delete a node, a pointer to the previous node is needed. To get this previous node, sometimes the list is traversed. In DLL, we can get the previous node using the previous pointer. 
Disadvantages of DLL over the singly linked list:
Every node of DLL Requires extra space for a previous pointer. It is possible to implement DLL with a single pointer though (See this and this). 
All operations require an extra pointer previous to be maintained. For example, in insertion, we need to modify previous pointers together with the next pointers. For example in the following functions for insertions at different positions, we need 1 or 2 extra steps to set the previous pointer.

# Insertion in DLL:

A node can be added in four ways:

* At the front of the DLL 
* After a given node. 
* At the end of the DLL 
* Before a given node.

1) Add a node at the front:
The new node is always added before the head of the given Linked List. And newly added node becomes the new head of DLL. For example, if the given Linked List is 1->0->1->5 and we add an item 5 at the front, then the Linked List becomes 5->1->0->1->5. Let us call the function that adds at the front of the list push(). The push() must receive a pointer to the head pointer because the push must change the head pointer to point to the new node.
2) Add a node after a given node:
We are given a pointer to a node as prev_node, and the new node is inserted after the given node.
3) Add a node at the end:
The new node is always added after the last node of the given Linked List. For example, if the given DLL is 5->1->0->1->5->2 and we add item 30 at the end, then the DLL becomes 5->1->0->1->5->2->30. Since a Linked List is typically represented by its head of it, we have to traverse the list till the end and then change the next of last node to the new node.
4) Add a node before a given node: 
Let the pointer to this given node be next_node and the data of the new node be added as new_data. Check if the next_node is NULL or not. If it’s NULL, return from the function because any new node can not be added before a NULL. Allocate memory for the new node, let it be called new_node. Set new_node->data = new_data. Set the previous pointer of this new_node as the previous node of the next_node, new_node->prev = next_node->prev. Set the previous pointer of the next_node as the new_node, next_node->prev = new_node. Set the next pointer of this new_node as the next_node, new_node->next = next_node; If the previous node of the new_node is not NULL, then set the next pointer of this previous node as new_node, new_node->prev->next = new_node. Else, if the prev of new_node is NULL, it will be the new head node. So, make (*head_ref) = new_node.


# Code Snippet
![image](https://user-images.githubusercontent.com/68808227/193597002-3f59a6be-b68e-4c51-ba22-e9523f6b85ba.png)


# Sample Output

Created DLL is:                                                                            
Traversal in forward direction                                                             
 1  7  5  8  6  4                                                                          
Traversal in reverse direction                                                             
 4  6  8  5  7  1 
 
 ![image](https://user-images.githubusercontent.com/68808227/193596119-099ef9cf-c5e6-4d45-af71-627785bb8303.png)
