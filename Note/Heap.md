# Heap
binary tree base data structure

the priority of parent >= priority of children

heap tree is a *complete binay tree*

    use array to achieve 
        children: (index * 2 + 1) / (index * 2 + 2)
        parent: (index - 1) / 2

#### compare
inplement comparable interface -> element type

create new comparactor 

use lambda expression

## PrioroityQueue
achieve complete binary tree

    node.key <= descendents.key

