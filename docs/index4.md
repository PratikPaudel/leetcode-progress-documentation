# DSA Conceptual

## LinkedList

<p> One disadvantage of using arrays to store data is that arrays are static structures and therefore cannot be easily extended or reduced to fit the
data set. Arrays are also expensive to maintain new insertions and deletions. </p> 

<p> A linked list is a linear, dynamic data structure where each node contains data and a reference to the next node. The list can grow or shrink as needed, with the head pointing to the first node, or null if the list is empty. The last node points to null. </p>

```mermaid

graph LR
    head
    A["4 | next"] --> B["15 | next "]
    B --> C["7 | next "]
    C --> D["1 | next "]
    D --> E[NULL]

    classDef noStroke fill:none,stroke:none;
    class head,E noStroke;
    
    classDef defaultStyle fill:none,stroke:#fff;
    class A,B,C,D defaultStyle;

```

<p> <b> Singly Linked List </b> </p>
Notes: To track the element, we need head node anda tail node. Last valid node with data stored is tail node. First node with data stored is head node. 
We get information from a node and then go to the next node information it has until the node points to null.

**Operations in LinkedList:**

### addFirst - O(1)

**Steps:**
1. Create a new node: `Node newNode = new Node(data);`
2. Point the next of the new node to the head: `newNode.next = head;`
3. Point the head to the new node: `head = newNode;`

``` java
public void addFirst(int data) {
    Node newNode = new Node(data);
    if (head == null) {
        head = tail = newNode;
        return;
    }
    newNode.next = head;
    head = newNode;
}
```
   
### addLast - O(1)

**Steps:**

1. Create a new node: `Node newNode = new Node(data);`
2. Point the next of the tail node to the newNode: `tail.next = newNode;`
3. Set the tail to the newNode: `tail = newNode;`

```java
public void addLast(int data) {
    Node newNode = new Node(data);
    if (head == null) {
        head = tail = newNode;
        return;
    }
    tail.next = newNode;
    tail = newNode;
}
```

### Print a linkedlist - O(N)

**Steps:**

1. Initialize a temporary node to traverse the list: Node temp = head;
2. Check if the list is empty:
3. If yes, print "The list is empty" and return.
4. Traverse through the list:
5. Print the data of the current node: System.out.print(temp.data);
6. Move to the next node: temp = temp.next;

> Note: You are traversing through an existing list, so you don't need to create any new nodes. 


```java
public void printList() {
    Node temp = head;
    if (head == null) {
        System.out.print("The list is empty");
        return;
    }
    while (temp != null) {
        System.out.print(temp.data);
        temp = temp.next;
    }
}
```

### Size of a linkedlist - O(N)

**Steps:**

1. Initialize a temporary node to traverse the list: Node temp = head;
2. Initialize a variable to store the size of the list: int size = 0;
3. Traverse through the list, keep adding to the variables. 
4. Return the size of the list.

```java
public int size() {
    Node temp = head;
    int size = 0;
    while (temp != null) {
        size++;
        temp = temp.next;
    }
    return size;
}
```

