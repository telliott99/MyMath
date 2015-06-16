.. _rotation:

########
Rotation
########

In this section we will take a brief look at some formulas for rotation of vectors or coordinate systems in two dimensions.

Start with a vector

.. math::

    \mathbf{A} = \langle x,y \rangle
    
where :math:`x` and :math:`y` are the number of units :math:`\mathbf{A}` extends in each direction.  An alternative notation would be to add the components in the standard coordinate system:

.. math::

    \mathbf{A} = x \mathbf{\hat{i}} + y \mathbf{\hat{j}}
    
where :math:`\mathbf{\hat{i}}` is the unit vector in the :math:`x`-direction, and :math:`\mathbf{\hat{j}}` is the unit vector in the :math:`y`-direction.

Now, let's think about how to rotate :math:`\mathbf{A}` by 90 degrees counter-clockwise to become :math:`\mathbf{A}'`.  

Drawing a dotted rectangle helps to visualize the change.  Whatever length the :math:`x`-coordinate of :math:`\mathbf{A}`, that same value will be the length of the :math:`y`-coordinate of the rotated vector :math:`\mathbf{A}'`.

.. image:: /figs/rotated_vec.png
   :scale: 50 %

Similarly, **minus** the :math:`y`-coordinate of :math:`\mathbf{A}` will become the :math:`x`-coordinate of :math:`\mathbf{A}'`.

The reason for the different sign of the second term should be apparent from consideration of the figure above.

===============
Matrix notation
===============

Matrix multiplication is particularly appropriate for this kind of transformation.  We write the rotation matrix :math:`T` for the previous transformation as

.. math::

    T = 
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
    x \\
    y
    \end{bmatrix}
    =
    \begin{bmatrix}
    -y \\
    x
    \end{bmatrix}

using the standard rules for matrix multiplication

=====================
Matrix multiplication
=====================

The rule is as follows.  The matrix multiplication

.. math::

    T \mathbf{A}

multiplies the *rows* of :math:`T` times the *columns* of :math:`\mathbf{A}`.  The entry in row 1, column 2 of the product is obtained by multiplying row 1 of :math:`T` times column 2 of :math:`\mathbf{A}`.  Multiply a row times a column by multiplying the components pairwise, then add them up.

In this example, we have the top element of the result, which is equal to :math:`-y`.  It was obtained by the following computation (row 1 times column 1):

.. math::

    T \mathbf{A} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}
    \begin{bmatrix}
    x \\
    y
    \end{bmatrix}
    =
    \begin{bmatrix}
    -y \\
    x
    \end{bmatrix}

    x' = 0 \times x + (-1) \times y = - y
    
    y' = 1 \times x + 0 \times y = x

============
General case
============

Rotation by 90 degrees is obviously a special case.  The general one involves some angle :math:`\theta`, and I bet you can guess that the formula will involve sine and cosine.  If we look again at the rotation matrix, I think we can also guess what the terms are in terms of the sine and cosine of :math:`\pi/2`:

.. math::

    T_{\pi/2} = 
    \begin{bmatrix}
    0 && -1 \\
    1 && \ \ 0
    \end{bmatrix}
    
    T_{\theta} = 
    \begin{bmatrix}
    \cos \theta && - \sin \theta \\
    \sin \theta && \ \cos \theta
    \end{bmatrix}

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

    x' = x \cos \theta - y \sin \theta
    
    y' = x \sin \theta + y \cos \theta

+++++++
Example
+++++++

Here is a second example which differs subtly from the first.  We want to transform the coordinates of the point (blue dot) from the familiar :math:`x,y`-coordinate system to a new system with rotated axes :math:`u,v`.

.. image:: /figs/min_rotation.png
       :scale: 25%

If you look at the figure, I hope that you will be able to figure out that to transform the vector :math:`\langle x, y \rangle` to :math:`\langle u, v \rangle`.

.. math::

    u = u_1 + u_2 = x \cos t + y \sin t

    v = v_2 - v_1 = x \sin t - y \cos t

And if you are *really* paying attention, you will see that there is a change of sign from the first example.  For this one:

.. math::
    
    T_{\theta} = 
    \begin{bmatrix}
    \cos \theta && \sin \theta \\
    -\sin \theta && \ \cos \theta
    \end{bmatrix}

The reason is that, in the second example, we rotated the coordinate system, not the vector or point.  Rotation of the coordinate system counter-clockwise is equivalent to rotating the point *clockwise*.  Hence the change of sign.
