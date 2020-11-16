---
title: 【Data Structure】Union-find data structure
tag: [Data Structure, Union-find, EN]
thumbnail: https://www.runoob.com/wp-content/uploads/2020/09/data-structure.png
category: Data Structure
---



## Definition

---
A disjoint-set data structure (also called union-find data structure) is a data structure that tracks a set of elements partitioned into a number of disjoint (overlapping) subsets.

## Operations
---
  - **Union**: Add new sets/merge existing sets
  - **Find**: Determine whether elements are in the same set

## Algorithm
---
  - The `representative element` (one without a parent, or whose parent is itself) is used to represent a subset
  - All the elements in a subset compose a tree structure whose root is `representative element`
  - if an element has a parent, the element is part of whatever set is identified by following the chain of parents upwards until a `representative element ` is reached at the root of the tree
  - If the `representative element` of the two elements is the same, then they belong to the same subset

## Code Snippets
---
### Initialization
---
#### Use a struct or class
```cpp
#define MAX 10000
struct Node
{
    int data;
    int rank;
    int parent;
}node[MAX]
```
#### Use arrays of the same size
```cpp
int set[max]; // the representative element of a subset where the certain element in
int rank[max];
int data[max];

void makeSet(int i){
    set[I]=i;
    rank[i]=0;
}
```

### Find Function
---
#### struct or class
```cpp
// find the representative element of a subset recursively
int find(int x){
    // if a node's parent is itself, then it is the representative element
    if(node[x].parent==x)
        return x;
    // else recursively find its parent
    return find(node[x].parent)
}
```

#### array
```cpp
int find(int i){
    // if a node's parent is itself, then it is the representative element
    if(set[i]==i)
        return set[i];
    // else recursively find its parent
    return find(set[i])
}
```
### Union
---
#### struct or class
```cpp
void union(int a, int b){
    a=find(a);
    b=find(b);
    if(node[a].rank>node[b].rank)
        node[b].parent=a;
    else{
        node[a].parent=b;
        if(node[a].rank==node[b].rank)
            node[b].rank++;
    }
}
```
#### array
```cpp
void union(int I, int j)
{
    I=find(I);
    j=find(j);
    if(i==j) return ;
    if(rank[i]>rank[j]) set[j]=i;
    else{
        if(rank[i]==rank[j]) rank[j]++;
        set[i]=j;
    }
}
```

## Related Problems
1. Compute the number of disjoint subsets -> count the number of nodes whose parent is itself, i.e. parent[i]==i
2. [Leetcode 990 - Satisfiability of Equality Equations](https://leetcode-cn.com/problems/satisfiability-of-equality-equations/)