# Introduction to Linear Algebra

	by	Gilbert Strang
		Massachusetts Institute of Technology

# Lec01 Geogetry meaning

<iframe src="https://www.geogebra.org/calculator/barfggqy?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>

**row picture**

<iframe src="https://www.geogebra.org/calculator/twzn2dwj?embed" width="800" height="600" allowfullscreen style="border: 1px solid #e4e4e4;border-radius: 4px;" frameborder="0"></iframe>


**column picture**



$$
x
\begin{bmatrix}
2 \\
-1 \\
0	
\end{bmatrix}

+

y
\begin{bmatrix}
-1 \\
2 \\
-3	
\end{bmatrix}

+

z
\begin{bmatrix}
0 \\
-1 \\
4	
\end{bmatrix}

=

\begin{bmatrix}
0 \\
-1 \\
4	
\end{bmatrix}

$$
***linear combination***

Can I solve every AX = b for every b?

Do the combinations of the columns fill all the three dimension space?

Ax = b

*matrix multiply by the vector*

$$

Ax = b \\

\begin{bmatrix}
2 & 5 \\
1 & 3 	
\end{bmatrix}

\begin{bmatrix}
1 \\
2	
\end{bmatrix}

= 

1
\begin{bmatrix}
2\\
1	
\end{bmatrix}

+

2
\begin{bmatrix}
5\\
3	
\end{bmatrix}\\

=

((2,5)\cdot(1,2), (1,3)\cdot(1,2))
$$


# Lect02 Matrix Elimination

$$
x + 2y + z = 2\\
3x + 8y + z = 12\\
	4y + z =2	\\
	
\begin{bmatrix}
1 & 2 & 1\\
3 & 8 & 1\\
0 & 4 & 1
\end{bmatrix}

\rightarrow

\begin{bmatrix}
1 & 2 & 1\\
0 & 2 & -2\\
0 & 4 & 1
\end{bmatrix}

\rightarrow

\begin{bmatrix}
1^p & 2 & 1\\
0 & 2^p & -2\\
0 & 0 & 5^p
\end{bmatrix}
pivot
$$

Elimination failure

When pivot $\neq$ 0, row exchange.

But in the end, the pivot = 0 means the elimination failed

Back substitution

$$
\begin{bmatrix}
1 & 2 & 1 & 2\\
3 & 8 & 1 & 12\\
0 & 4 & 1 & 2
\end{bmatrix}

\rightarrow

\begin{bmatrix}
1 & 2 & 1 & 2\\
0 & 2 & -2 & 6\\
0 & 4 & 1 & 2
\end{bmatrix}

\rightarrow

\begin{bmatrix}
1 & 2 & 1 & 2\\
0 & 2 & -2 & 6\\
0 & 0 & 5 & - 10
\end{bmatrix}
$$
augmented matrix $Ux = c$

$$
x + 2y + z = 2\\
	2y -2z = 6\\
		5z = -10
$$

$$
\begin{bmatrix}
- & - & -\\
- & - & -\\
- & - & -
\end{bmatrix}

\begin{bmatrix}
3 \\
4 \\
5
\end{bmatrix}

=

3col1 + 4col2 + 5col3\\

matrix \times column = column\\

\begin{bmatrix}
1&2&7
\end{bmatrix}

\begin{bmatrix}
- & - & -\\
- & - & -\\
- & - & -
\end{bmatrix}

=

1row1 + 2row2 + 7row3\\

row \times matrix = row\\
$$

$$
*\ left\ multiply\ row\\
*\ right\ multiply\ column
$$

Matrix

$$
\begin{bmatrix}
1 & 0 & 0\\
-3& 1 & 0\\
0 & 0 & 1	
\end{bmatrix}
\begin{bmatrix}
1 & 2 & 1 \\
3 & 8 & 1 \\
0 & 4 & 1 
\end{bmatrix}

= 

\begin{bmatrix}
1 & 2 & 1\\
0 & 2 & -2\\
0 & 4 & 1
\end{bmatrix}
$$

elementary matrix

$E_{21}$

$E_{32}(E_{21}A) = U$

$(E_{32}E_{21})A = U$ 

*assiociative law*


Permutation

Exchange row 1 and 2
$$
\begin{bmatrix}
0 & 1\\
1 & 0	
\end{bmatrix}

\begin{bmatrix}
a & b \\
c & d	
\end{bmatrix}

=

\begin{bmatrix}
c & d \\
a & b	
\end{bmatrix}
$$

$PA = U$

## Inverse matrix

$$
\begin{bmatrix}
1 & 0 & 0\\
3 & 1 & 0\\
0 & 0 & 1	
\end{bmatrix}
\begin{bmatrix}
1 & 0 & 0\\
-3& 1 & 0\\
0 & 0 & 1	
\end{bmatrix}

=

\begin{bmatrix}
1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1	
\end{bmatrix}
$$

$E^{-1}E = I$

# Lect03 Matrix Multiplication && Inverse

$$
\begin{bmatrix}
- & - & -\\
- & - & -\\
- & - & -
\end{bmatrix}
\begin{bmatrix}
- & - & -\\
- & - & -\\
- & - & -
\end{bmatrix}
=
\begin{bmatrix}
- & - & -\\
- & - & -\\
- & - & -
\end{bmatrix}
$$

$AB = C$

$$
C_{34} = row3\ of\ A \cdot column4\ of\ B\\
=a_{31}\cdot b_{14} + a_{32}\cdot b_{24} + \cdots\\
=\sum^{n}_{k = 1}{a_{3k}b_{k4}}
$$
$m\times n \cdot n \times p = m \times p$

column1 of B give the combination of the A column = column1 of C

row1 of A give the combination of the B row = row1 of C

$$
\begin{bmatrix}
2 & 7 \\
3 & 8 \\
4 & 9
\end{bmatrix}
\begin{bmatrix}
1 & 6\\
0 & 0
\end{bmatrix}

=

\begin{bmatrix}
2 \\
3 \\
4
\end{bmatrix}
\begin{bmatrix}
1 & 6	
\end{bmatrix}

+

\begin{bmatrix}
7 \\
8 \\
9
\end{bmatrix}
\begin{bmatrix}
0 & 0	
\end{bmatrix}
$$

C is the sum of (column of A) $\cdot$ (row of B)

$\sum^n_{k}{colA_{k}\times rowB_{k}}$

## Block Multiplication

$$
\begin{bmatrix}
A_{1} & A_{2}\\
A_{3} & A_{4}	
\end{bmatrix}

\begin{bmatrix}
B_{1} & B_{2}\\
B_{3} & B_{4}	
\end{bmatrix}

=

\begin{bmatrix}
- & -\\
- & -	
\end{bmatrix}
$$

