# Introduction to Linear Algebra

	by	Gilbert Strang
		Massachusetts Institute of Technology
---
MIT 18.06SC Linear Algebra, Fall 2011
# Lec01 The Geogetry of Linear Equations

n linear equations, n unknowns;
- Row picture
- Column picture *
- Matrix form
  
```
2x -  y = 0		
-x + 2y = 3    

[ 2 -1   [ x   = [ 0
 -1  2 ]   y ]     3 ]

    A      X   =   b
```
<!-- <iframe src="https://www.geogebra.org/calculator/barfggqy?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe> -->

Row picture

---

<!-- <iframe src="https://www.geogebra.org/calculator/twzn2dwj?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe> -->


Column picture

---

Find b linear combination of columns.
What's the combination?
It's will fill all plane.

```
2x -  y      = 0
-x + 2y -  z = -1
    -3y + 4y = 4

    [ 2 -1 0       [ 0  
A =   1 2 -1   b =  -1  
      0 -3 4 ]       4 ]  
```
$Linear\ Combination$

```
 [ 2     [ -1      [ 0   [ 0
x  1  + y   2   + z -1  = -1
   0 ]     -3 ]      4 ]   4 ]
```


Can I solve every AX = b for every b?

Do the combinations of the columns fill all the 3D space?

9 equations, 9 unknowns.
When the column is not independent: col9 = col7 + col8
We can get 8D space.

matrix multiply by the vector

Ax = b 
```
[ 2 5   [ 1  = 1 [ 2  + 2 [ 5  = [ 12
  1 3 ]   2 ]      1 ]      3 ]     7 ]
```
AX is a comb. of column of A.

Dot product
```
[ 2 5   [ 1  = | 2 5 | [ 1  + | 1 3 | [ 1  = [ 12   =
  1 3 ]   2 ]            2 ]            2 ]     7 ] 
((2,5) . (1,2), (1,3) . (1,2))
```

* Recitation
```
Solve 2x + y = 3, and find out
       x -2y = -1
its "row picture" and "column picture"
[ 2   x + [ 1   y  = [ 3
  1 ]      -2 ]       -1 ]
  v1        v2
A = [ v1, v2 ] = [ 2  1
                   1 -2 ]
v1 + v2 = [ 3
           -1 ]
A^{-1}A = [ 1 0
            0 1 ]
X = A^{-1}[ 3
           -1 ]
```

# Rec 1 | MIT 18.085 Computational Science and Engineering I, fall 2008
Vectors / Matrices / Subspaces

# Lect02 Matrix Elimination

$Elimination$
```
 x + 2y + z = 2
3x + 8y + z = 12
	 4y + z = 2	
	
[ |1| 2  1      [ |1| 2  1      [ |1|  2   1
   3  8  1   ->    0 |2| -2  ->    0  |2| -2
   0  4  1 ]       0  4  1 ]       0   0  |5| ]
```
pivot

Elimination failure

When pivot $\neq$ 0, row exchange.

But in the end, the pivot = 0 means the elimination failed

$Back\ substitution$
```
[ 1 2 1 |2     [ 1 2 1  |2    [1 2 1  |2
  3 8 1 |12 ->   0 2 -2 |6 ->  0 2 -2 |6
  0 4 1 |2 ]     0 4 1  |2]    0 0 5  |-10]
```
augmented matrix $Ux = c$
```
x + 2y + z = 2
	  2y -2z = 6
		    5z = -10

[ - - -     [ 3
  - - -   *   4  = 3col1 + 4col2 + 5col3
  - - - ]     5]

matrix * column = column

[ 1     [ - - -
  2   *   - - -   = 1row1 + 2row2 + 7row3
  7 ]     - - - ]

row * matrix = row
```

Matrix
```
[ 1 0 0     [ 1 2 1     [ 1 2 1
 -3 1 0   *   3 8 1   =   0 2 -2
  0 0 1 ]     0 4 1 ]     0 4 1 ]
[  1row1 + 0row2 + 0row3
  -3row1 + 1row2 + 0row3
   0row1 + 0row2 + 1row3 ]
```

Elementary Matrix

$E_{21}$ element at (2, 1) -> 0

$E_{32}(E_{21}A) = U$

$(E_{32}E_{21})A = U$ 

$Permutation$

Exchange row1 and row2
```
[ 0 1   * [ a b   = [ c d 
  1 0 ]     c d ]     a b ]
```
$PA = U$
Exchange column1 and column2
```
[ a b    [ 0 1    = [ b a
  c d ]    1 0 ]      d c ]
```
## Inverse matrix
```
[ 1 0 0  [ 1 0 0   [ 1 0 0
  3 1 0   -3 1 0  =  0 1 0
  0 0 1	]  0 0 1 ]   0 0 1 ]
```
$E^{-1}E = I$
* Recitation
```
Solve, using method of elimination:

```
# Lect03 Multiplication and Inverse Matrices

```
[ - - -   [ - - -     [ - - -
  - - -     - - -   =   - - -
  - - - ]   - - - ]     - - - ]

```
$AB = C$


C_{34}  = row3 of A * column4 of B  
        = $a_{31}\cdot b_{14} + a_{32}\cdot b_{24} + \cdots$  
        = $\sum^{n}_{k = 1}{a_{3k}b_{k4}}$

$m\times n \cdot n \times p = m \times p$

column1 of B give the combination of the A column = column1 of C

row1 of A give the combination of the B row = row1 of C



2 7 
3 8 
4 9


1 6
0 0


=


2 
3 
4


1 6	


+


7 
8 
9


0 0	



C is the sum of (column of A) $\cdot$ (row of B)

$\sum^n_{k}{colA_{k}\times rowB_{k}}$

## Block Multiplication



A_{1} A_{2}
A_{3} A_{4}	



B_{1} B_{2}
B_{3} B_{4}	


=


- -
- -	

