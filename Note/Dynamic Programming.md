# Dynamic Programming

find the induction from an single example to the common or rule.

#### process
1. get the informatin
2.  enumerate cases
3.  find the rule
4.  describe the induction rule as math expression
5.  prove accurarcy

## 1D 
**lnear scan & look back**

M[i] & M[i - 1] & M[i - 2]
> memory list -> physical significance & interval (depend on the question)

> left -> use memory list
> 
> right -> calculate 

## 2D

M[i][j] & M[i - 1][j - 1] & M[i - 1][j] & M[i][j - 1]

## prefix sum

the sum from i to j <- M[j] + M[i] + input[i]

### Time Complexity
number of distinctive state * number of dependent states of a single state * time spend at aclculating