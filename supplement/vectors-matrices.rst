.. _vectors-matrices:

####################
Vectors and Matrices
####################

There is a close connection between points in the plane and vectors in two-dimensional space.  We can think of each of them as an *ordered* pair of numbers.

.. math::

    P = (P_x, P_y)
    
The vector :math:`\mathbf{p}` that extends from the origin to the point :math:`P` has both a length and a direction in space (the usual definition of a vector as a mathematical object), but another way to view :math:`\mathbf{p}` is to write out the components in terms of the :math:`x,y`-coordinate system.

.. math::

    \mathbf{p} = \langle p_x, p_y \rangle

where :math:`P_x = p_x` and :math:`P_y = p_y`.

And yet another common representation is in terms of the *unit vectors* along the :math:`x` and :math:`y`-axes.

.. math::

    \mathbf{\hat{i}} = \langle 1, 0 \rangle

    \mathbf{\hat{j}} = \langle 0, 1 \rangle

with these definitions, we can write:

.. math::

    \mathbf{p} = \langle p_x, p_y \rangle 
    
    = p_x \mathbf{\hat{i}} + p_y \mathbf{\hat{j}}
    
    = p_x \langle 1, 0 \rangle + p_y \langle 0, 1 \rangle
    
    = \langle p_x, 0 \rangle + \langle 0, p_y \rangle

    = \langle p_x, p_y \rangle

Finally, a third notation for vectors is column format:

.. math::
    
    \mathbf{p} =
    \begin{bmatrix}
    p_x \\
    p_y
    \end{bmatrix}

==============
Matrix algebra
==============

The last notation is actually matrix notation in disguise.  You may have seen these in pre-calculus, to hold the coefficients when solving a *system* of equations.  For this system

.. math::

    x + 2y = 5
    
    2x + y = 4
    
we write the components as

.. math::
    
    M =
    \begin{bmatrix}
    1 && 2 \\
    2 && 1
    \end{bmatrix}

Matrices have an important use in linear algebra, where we think of them as carrying out transformations on vectors.  For example, the matrix we are interested in here carries out rotation of a vector to a new orientation in the plane without changing its length.  

Matrices for different transformations can be combined by means of matrix multiplication.  The rule for matrix multiplication is to multiply rows by columns.  The simplest way to explain it is to just show an example:

.. math::

    A \times B = C
    
    \begin{bmatrix}
    a && b \\
    c && d
    \end{bmatrix}
    \times
    \begin{bmatrix}
    e && f \\
    g && h
    \end{bmatrix}
    =
    \begin{bmatrix}
    ae + bg && af + bh \\
    ce + dg && cf + dh
    \end{bmatrix}

The recipe here is as follows:  to compute the entry in the product matrix at row :math:`m`, column :math:`n`, we take row :math:`m` of matrix :math:`A` and multiply it by column :math:`n` of matrix :math:`B` as follows:

.. math::

    C_{mn} = \langle a,b \rangle \ \cdot \langle e,g \rangle
    
    = ae + bg

The symbol :math:`\cdot` means "dot product", for more see:

https://en.wikipedia.org/wiki/Dot_product

We write the result in row :math:`m`, column :math:`n` of the matrix :math:`C`.  Here is a graphic from wikipedia:

.. image:: /figs/mm1.png
       :scale: 25%
       
To multiply a matrix times a vector, it is simpler because the vector has only a single column.

.. math::

    T \times \mathbf{p} = \mathbf{q}
    
    \begin{bmatrix}
    t_{11} && t_{12} \\
    t_{21} && t_{22}
    \end{bmatrix}
    \times
    \begin{bmatrix}
    p_x \\
    p_y
    \end{bmatrix}
    =
    \begin{bmatrix}
    q_x \\
    q_y
    \end{bmatrix}

where

.. math::

    q_x = t_{11} \ p_x + t_{12} \ p_y

    q_y = t_{21} \ p_x + t_{22} \ p_y

=====================
An example:  rotation
=====================

Let's look at a particular example:  90 degree counter-clockwise rotation.  Suppose :math:`\mathbf{A} = \langle a_x, a_y \rangle = \langle 3, 1 \rangle`.  Then :math:`\mathbf{A'} = \langle a'_x, a'_y \rangle = \langle -1, 3 \rangle`.

.. image:: /figs/rotated_vec.png
       :scale: 25%

Matrix multiplication is particularly appropriate for this kind of transformation.  We write the rotation matrix :math:`T` for the previous transformation as

.. math::

    T_{90, \ \text{ccw}} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}

Then the rotation operation is just:

.. math::

    T \mathbf{A} = \mathbf{A}'

expanded:

.. math::

    T \mathbf{A} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}
    \begin{bmatrix}
    a_x \\
    a_y
    \end{bmatrix}
    =
    \mathbf{A'}
    =
    \begin{bmatrix}
    -a_y \\
    a_x
    \end{bmatrix}


    T \mathbf{A} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}
    \begin{bmatrix}
    3 \\
    1
    \end{bmatrix}
    =
    \mathbf{A'}
    =
    \begin{bmatrix}
    -1 \\
    3
    \end{bmatrix}

using the standard rules for matrix multiplication.

To obtain the first component :math:`a_x'` of the result (which has the value :math:`-1`), we did this multiplication:

.. math::

    a_x' = 0 \times a_x + (-1) \times a_y = - 1
    
This can be understood as a multiplication component-wise of the first row of T times the column vector :math:`\langle a_x, a_y \rangle`.  In the same way, the second component :math:`a_y'` of the result (has the value :math:`3`), obtained by this multiplication:

.. math::

    a_y' = 1 \times a_x + 0 \times a_y = 3

============
General case
============

Rotation by 90 degrees is obviously a special case.  The general case involves some angle :math:`\theta`, and I bet you can guess that the formula will involve the sine and cosine of the angle :math:`\theta`.  If we look again at the rotation matrix, I think you might also guess what the formulas are in terms of the sine and cosine of :math:`\pi/2`:

.. math::

    T_{90, \ \text{ccw}} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}
    
    T_{\theta} = 
    \begin{bmatrix}
    \cos \theta && - \sin \theta \\
    \sin \theta && \ \cos \theta
    \end{bmatrix}

Here, we agree that the angle :math:`\theta` refers to counter-clockwise rotation of a vector or a point in cartesian coordinates.

This is not so much a derivation as an aid to memory.  It is how I remember the general formula.

If we write out the matrix multiplication as two equations, we obtain an equivalent and perhaps more familiar formula.

.. math::
    
    T_{\theta} \mathbf{A} = 
    \begin{bmatrix}
    \cos \theta && - \sin \theta \\
    \sin \theta && \ \cos \theta
    \end{bmatrix}
    \begin{bmatrix}
    x \\
    y
    \end{bmatrix}
    =
    \begin{bmatrix}
    x \cos \theta - y \sin \theta  \\
    x \sin \theta + y \cos \theta
    \end{bmatrix}
    =
    \begin{bmatrix}
    x' \\
    y'
    \end{bmatrix}
    

    x' = x \cos \theta - y \sin \theta
    
    y' = x \sin \theta + y \cos \theta


