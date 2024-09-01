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

