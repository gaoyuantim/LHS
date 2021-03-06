## Guide
In this files there are three programs using the iteration methods in Matlab environment.

  Input in the Command window of Matlab : 

    [Table , D2] = filename(n,m)

Here, _m_ is dimension, _n_ is number of points. _filename_ depends on which algorithm you choose.

## Examples

## Example with LHS_2

Input:
```matlab
LHS_2(6,3)
```

Output:
```
 0 | 1 | 2 | 3 | 4 | 5 
 1 | 3 | 4 | 0 | 5 | 2
 2 | 5 | 0 | 4 | 3 | 1
```

## Example with LHS_Optimal

Input:
```
LHS_Optimal(6,3)
```

Output:
```
 0 | 1 | 2 | 3 | 4 | 5 
 1 | 3 | 4 | 0 | 5 | 2
 1 | 5 | 2 | 3 | 0 | 4
```

## About the algorithms

Totally the method realizing the ergodicity in the programs is same but we use two different structures to realize the iteration. 

In the program LHS_Optimal, we calculate every possible construction of points to find out the maximin. According to the article : _An efficient algorithm for constructing optimal design of computer experiments_ by Ruichen Jin, Wei Chen and Agus Sudjianto, just a part of the values need to be changed each time.

In the program `LHS_2.c`, we change another method of comparison. For
example, we would like to find maximin of N points in a space of M
dimensions. Now we decide a construction of n points in m dimensions
and m < M, then we calculate all the possibility to find out the
maximin for the rest dimensions with the result of the prior
dimensions. After that we return the value of maximin to the previous
dimension, and in the layer of previous dimension, we will gather all
the maximins with different distribution in this dimension and return
the max to its previous. At last, we will get the maximin for the
space.

In the program `LHS_Optimal.c`, at last we get a normal group of
points and a maximin value. But by the program `LHS_Optimal.c`, we can
get a optimal result according to the criteria in standard in the
article: _Exploratory designs for computational experiments_ by Max
D.Morris and Toby J.Mitchell.

At last, all the results meaningful we get are stored in the folder file.
