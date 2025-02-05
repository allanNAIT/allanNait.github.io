---
layout: page
title: Determinants & Inverses
---
## Introduction
Previously the work with matrices has been multiplication, scaling, and linear transformations. With linear transformations, it was found that an object could be moved, and scaled in 2D and 3D space. This lesson will focus on getting the object back to its original position.

## Determinants
### Key Concepts
The key concepts for this part of the lesson are:
* Definition of a determinant
* Calculating a determinant for a 2x2, 3x3, and 4x4 matrices

## Lesson
Every square matrix has a special property called the determinant. The determinant is used to create an inverse matrix from a given matrix such that <img src="https://latex.codecogs.com/svg.latex?\large&space;M\times{M^{-1}=I"/>. Not every square matrix has an inverse, as will be covered later in this lesson, but for now that is the purpose of covering determinants. It is important to get an understanding of what a determinant is before it is calculated.

#### 2x2 Determinants
Given the matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M=\left[\begin{array}{cc}3&1\\1&2\end{array}\right]"/>

The matrix can be graphically represented by plotting its basis vectors and creating a parallelogram with the determinant of the matrix equal to the area of the parallelogram:

![parallelogram](files/parallelogram.jpg)

Now that a determinant of a 2x2 matrix can be shown graphically the next step is to compute the determinant mathematically. The determinant of **M** is written as <img src="https://latex.codecogs.com/svg.latex?\large&space;detM"/> or <img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert"/> (note this symbol is not the absolute value).

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}M_{11}&M_{12}\\M_{21}&M_{22}\end{array}\right|=M_{11}M_{22}-M_{12}M_{21}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}3&1\\1&2\end{array}\right|=(3)(2)-(1)(1)=5"/>

The computed value of a determinant is not always a positive number; it can be negative or even zero. For example, given the matrix below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}-3&2\\4&5\end{array}\right|=(-3)(5)-(2)(4)=-23"/>

![determinant-calculation-2-x-2](files/determinant-calculation-2-x-2.jpg)

#### 3x3 Determinants
Now what about a 3x3 matrix? Since a 3D matrix has 3 basis vectors the geometric shape would be a parallelogram extended to 3 dimensions creating a parallelepiped. In this case the determinant would be the volume of the parallelepiped as shown in the below:

![parallelepiped](files/parallelepiped.jpg)

Note in figure above that each side of the parallelepiped is ”extruded” from the plane created by only two of the matrix basis vectors, thus creating the 3D shape. The matrix used for this figure is show below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{ccc}2&5&1\\1&2&5\\4&3&4\end{array}\right|"/>

Now that a determinant of a 3x3 matrix can be shown graphically the next step is to compute the determinant mathematically. Starting with what is known about the determinant of a 2x2 matrix a pattern can be created:<br>
![math-2-x-2-determinant](files/math-2-x-2-determinant.jpg)

The pattern is the diagonals from left to right are **+** and the diagonals from right to left are **-**. To do this math the 3x3 matrix needs to be duplicated and the duplicate written beside it as shown below:<br>
![math-3-x-3-determinant](files/math-3-x-3-determinant.jpg)

This results in the equation:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{ccc}M_{11}&M_{12}&M_{13}\\M_{21}&M_{22}&M_{23}\\M_{31}&M_{32}&M_{33}\end{array}\right|"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;=M_{11}M_{22}M_{33}+M_{12}M_{23}M_{31}+M_{13}M_{21}M_{31}-M_{13}M_{22}M_{31}-M_{12}M_{21}M_{33}-M_{11}M_{23}M_{32}"/>

Now using the 3D matrix, the calculation of its determinant is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{ccc}2&5&1\\1&2&5\\4&3&4\end{array}\right|=(2)(2)(4)+(5)(5)(4)+(1)(1)(3)-(1)(2)(4)-(5)(1)(4)-(2)(3)(5)"/>
<img src="https://latex.codecogs.com/svg.latex?\large&space;=16+100+3-8-20-30=61"/>

![determinant-calculation-3-x-3](files/determinant-calculation-3-x-3.jpg)

This method of calculating the determinant of a 3x3 matrix does not extend to the calculation of the determinant of a 4x4 matrix. The correct process uses determinants of 2x2 matrices:

Given <img src="https://latex.codecogs.com/svg.latex?\large&space;M=\left[\begin{array}{ccc}M_{11}&M_{12}&M_{13}\\M_{21}&M_{22}&M_{23}\\M_{31}&M_{32}&M_{33}\end{array}\right]"/>

then

<img src="https://latex.codecogs.com/svg.latex?\large&space;det(M)=M_{11}\times{det\left[\begin{array}{cc}M_{22}&M_{23}\\M_{32}&M_{33}\end{array}\right]}-M_{12}\times{det\left[\begin{array}{cc}M_{21}&M_{23}\\M_{31}&M_{33}\end{array}\right]}+M_{13}\times{det\left[\begin{array}{cc}M_{21}&M_{22}\\M_{31}&M_{32}\end{array}\right]}"/>

Expanding this out we get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;det(M)=M_{11}(M_{22}M_{33}-M_{23}M_{32})-M_{12}(M_{21}M_{33}-M_{23}M_{31})+M_{13}(M_{21}M_{32}-M_{22}M_{31})"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;det(M)=M_{11}M_{22}M_{33}-M_{11}M_{23}M_{32}-M_{12}M_{21}M_{33}+M_{12}M_{23}M_{31}+M_{13}M_{21}M_{32}-M_{13}M_{22}M_{31}"/>

Comparing this result with the previous result shows the answer will be the same. Unfortunately, the calculation of the determinant of a 4x4 matrix MUST use this proper method (above), and not expanding on the original 3x3 determinant calculation.

#### 4x4 Determinants
If we use the pattern from the 3x3 determinant calculation, you will NOT get the correct determinant value. Instead, you need to use the following pattern:

Given matrix <img src="https://latex.codecogs.com/svg.latex?\large&space;M=\left[\begin{array}{cccc}M_{11}&M_{12}&M_{13}&M_{14}\\M_{21}&M_{22}&M_{23}&M_{24}\\M_{31}&M_{32}&M_{33}&M_{34}\\M_{41}&M_{42}&M_{43}&M_{44}\end{array}\right]"/>

then

<img src="https://latex.codecogs.com/svg.latex?\large&space;det(M)=M_{11}\times{det\left[\begin{array}{ccc}M_{22}&M_{23}&M_{24}\\M_{32}&M_{33}&M_{34}\\M_{42}&M_{43}&M_{44}\end{array}\right]-M_{12}\times{det\left[\begin{array}{ccc}M_{21}&M_{23}&M_{24}\\M_{31}&M_{33}&M_{34}\\M_{41}&M_{43}&M_{44}\end{array}\right]"/><br><img src="https://latex.codecogs.com/svg.latex?\large&space;+M_{13}\times{det\left[\begin{array}{ccc}M_{21}&M_{22}&M_{24}\\M_{31}&M_{32}&M_{34}\\M_{41}&M_{42}&M_{44}\end{array}\right]-M_{14}\times{det\left[\begin{array}{ccc}M_{21}&M_{22}&M_{23}\\M_{31}&M_{32}&M_{33}\\M_{41}&M_{42}&M_{43}\end{array}\right]"/>


## Inverses
### Key Concepts
The key concepts for this part of the lesson are:
* Create an inverse matrix for 2x2 and 3x3 matrices
* Prove that the inverse matrix satisfies the equation <img src="https://latex.codecogs.com/svg.latex?\large&space;M\times{M^{-1}=I"/>

### Lesson
Previously it was given that the inverse of a matrix satisfies the equation <img src="https://latex.codecogs.com/svg.latex?\large&space;M\times{M^{-1}=I"/>. For a 2x2 matrix the inverse is calculated as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M^{-1}=\frac{1}{detM}M^{'}"/> where <img src="https://latex.codecogs.com/svg.latex?\large&space;M^{'}=\left[\begin{array}{cc}M_{22}&-M_{12}\\-M_{21}&M_{11}\end{array}\right]"/>

Example using the previous 2x2 matrices:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}-3&2\\4&5\end{array}\right|=(-3)(5)-(2)(4)=-23"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M^{-1}=\frac{1}{-23}\left[\begin{array}{cc}5&-2\\-4&-3\end{array}\right]=\left[\begin{array}{cc}-0.2174&0.0870\\0.1739&0.1304\end{array}\right]"/>

![inverse-2-x-2-calculation](files/inverse-2-x-2-calculation.jpg)

For 3x3, and 4x4 matrices, the method used to calculate the inverse is called the Adjoint method. The creation of an Adjoint Matrix involves creating a new matrix which is made up of cofactors, calculating the determinant of each cofactor matrix, then transposing the matrix. Lastly the inverse of a matrix is computed as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M^{-1}=\frac{adj(M)}{\vert{M}\vert}"/>

As this equation involves dividing each element of the Adjoint Matrix by a determinant, if the determinant is zero the given matrix has no computable inverse.

In the previous example the determinant was computed to be 61:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{ccc}2&1&4\\5&2&3\\1&5&4\end{array}\right|=2\left|\begin{array}{cc}2&5\\3&4\end{array}\right|-5\left|\begin{array}{cc}1&5\\4&4\end{array}\right|+1\left|\begin{array}{cc}1&2\\4&3\end{array}\right|"/><br><br>
<img src="https://latex.codecogs.com/svg.latex?\large&space;=2((2)(4)-(5)(3))-5((1)(4)-(5)(4))+1((1)(3)-(2)(4))=2(8-15)-5(4-20)+1(3-8)=2(-7)-5(-16)+1(-5)=-14+80-5=61"/>

which is not zero, therefore the inverse of the given matrix can be computed.

<img src="https://latex.codecogs.com/svg.latex?\large&space;adj(M)={\left[\begin{array}{ccc}C^{\{11\}}&-C^{\{12\}}&C^{\{13\}}\\-C^{\{21\}}&C^{\{22\}}&-C^{\{23\}}\\C^{\{31\}}&-C^{\{32\}}&C^{\{33\}}\end{array}\right]}^T"/>

Each of the elements of the `adjoint` array are called `cofactors`.

To find a cofactor matrix, such as <img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{11\}}"/> do the following:
* Eliminate the first row and the first column on the matrix
* Calculate the determiniant of the resulting 2x2 matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{11\}}=\left|\begin{array}{cc}2&3\\5&4\end{array}\right|=-7"/>

To find a cofactor matrix, such as <img src="https://latex.codecogs.com/svg.latex?\large&space;-C^{\{12\}}"/> do the following:
* Eliminate the first row and the second column on the matrix
* Calculate the determiniant of the resulting 2x2 matrix multiplied by -1:

<img src="https://latex.codecogs.com/svg.latex?\large&space;-C^{\{12\}}=-\left|\begin{array}{cc}5&3\\1&4\end{array}\right|=-17"/>

To find a cofactor matrix, such as <img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{13\}}"/> do the following:
* Eliminate the first row and the third column on the matrix
* Calculate the determiniant of the resulting 2x2 matrix

<img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{13\}}=\left|\begin{array}{cc}5&2\\1&5\end{array}\right|=23"/>

The next row of the matrix produces the following cofactors:

<img src="https://latex.codecogs.com/svg.latex?\large&space;-C^{\{21\}}=-\left|\begin{array}{cc}1&4\\5&4\end{array}\right|=16"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{22\}}=\left|\begin{array}{cc}2&4\\1&4\end{array}\right|=4"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;-C^{\{23\}}=-\left|\begin{array}{cc}2&1\\1&5\end{array}\right|=-9"/>

Finally, the last row of the matrix produces the following cofactors:

<img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{31\}}=-\left|\begin{array}{cc}1&4\\2&3\end{array}\right|=-5"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;-C^{\{22\}}=-\left|\begin{array}{cc}2&4\\5&3\end{array}\right|=14"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;C^{\{33\}}=\left|\begin{array}{cc}2&1\\5&2\end{array}\right|=-1"/>

Time to put all the cofactors together and calculate the Adjoint matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;adj(M)={\left[\begin{array}{ccc}C^{\{11\}}&-C^{\{12\}}&C^{\{13\}}\\-C^{\{21\}}&C^{\{22\}}&-C^{\{23\}}\\C^{\{31\}}&-C^{\{32\}}&C^{\{33\}}\end{array}\right]}^T={\left[\begin{array}{ccc}-7&-17&23\\16&4&-9\\-5&14&-1\end{array}\right]}^T=\left[\begin{array}{ccc}-7&16&-5\\-17&4&14\\23&-9&-1\end{array}\right]"/>

Now that the Adjoint matrix is computed the next step is to compute the inverse (for ease of calculations leave values as fractions when demonstrating this to avoid decimal rounding errors):

<img src="https://latex.codecogs.com/svg.latex?\large&space;M^{-1}=\frac{1}{61}\left[\begin{array}{ccc}-7&16&-5\\-17&4&14\\23&-9&-1\end{array}\right]=\left[\begin{array}{ccc}\frac{-7}{61}&\frac{16}{61}&\frac{-5}{61}\\\frac{-17}{61}&\frac{4}{61}&\frac{14}{61}\\\frac{23}{61}&\frac{-9}{61}&\frac{-1}{61}\end{array}\right]\approx{\left[\begin{array}{ccc}-0.1148&0.2623&-0.0820\\-0.2787&0.0656&0.2295\\0.3770&-0.1475&-0.0164\end{array}\right]}"/>

Time to prove that <img src="https://latex.codecogs.com/svg.latex?\large&space;M\times{M^{-1}}=I"/>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}2&1&4\\5&2&3\\1&5&4\end{array}\right]\times{\left[\begin{array}{ccc}\frac{-7}{61}&\frac{16}{61}&\frac{-5}{61}\\\frac{-17}{61}&\frac{4}{61}&\frac{14}{61}\\\frac{23}{61}&\frac{-9}{61}&\frac{-1}{61}\end{array}\right]}=\left[\begin{array}{ccc}\frac{-14-17+92}{61}&\frac{32+4-36}{61}&\frac{-10+14-4}{61}\\\frac{-35-34+69}{61}&\frac{80+8-27}{61}&\frac{-25+28-3}{61}\\\frac{-7-85+92}{61}&\frac{16+20-36}{61}&\frac{-5+70-4}{61}\end{array}\right]=\left[\begin{array}{ccc}1&0&0\\0&1&0\\0&0&1\end{array}\right]"/>

![inverse-3-x-3-calculation](files/inverse-3-x-3-calculation.jpg)

As an extension computing the inverse of a 4x4 matrix is also possible and is necessary when using the 4D homogeneous coordinate system. The one change that needs to be made is for the Adjoint matrix as shown below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;adj(M)={\left[\begin{array}{cccc}C^{\{11\}}&-C^{\{12\}}&C^{\{13\}}&-C^{\{14\}}\\-C^{\{21\}}&C^{\{22\}}&-C^{\{23\}}&C^{\{24\}}\\C^{\{31\}}&-C^{\{32\}}&C^{\{33\}}&-C^{\{34\}}\\-C^{\{41\}}&C^{\{42\}}&-C^{\{43\}}&C^{\{44\}}\end{array}\right]}^T"/>

With each of the cofactors needing to have a determinant of a 3x3 matrix.

![inverse-4-x-4-calculation](files/inverse-4-x-4-calculation.jpg)

## Exercises & Assignments
Complete the [Determinants & Inverses worksheet](matrix-worksheet-3.md). Once complete proceed to Moodle to complete Knowledge Check 07 - Determinants & Inverses (strongly recommended to be completed prior to attempting Lab 2).

#### [Outcome Home](index.md)
#### [PHYS1521 Home](../)
