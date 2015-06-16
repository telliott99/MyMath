.. _rotation:

###################
Rotation of Vectors
###################

In this section we will take a look at some formulas for rotation of vectors and coordinate systems in two dimensions.

The first observation is that these two types of rotation are in a sense, opposites.

.. image:: /figs/rotate_vec_coord.png
   :scale: 50 %

In the left panel, we have a vector :math:`\mathbf{A}` that is rotated *clockwise* by 30 degrees (:math:`\pi/6`) to give vector :math:`\mathbf{A}'`.  In the right hand panel, we have instead rotated the coordinate system *counter-clockwise* by 30 degrees to give new axes :math:`u` and :math:`v`.

Both operations end up with the same relationship between vector and coordinate system.  The length of the projection of :math:`\mathbf{A}'` onto the :math:`x`-axis in the left panel is equal to the length of the projection of vector :math:`\mathbf{A}` onto the :math:`u`-axis in the left panel, and likewise for :math:`y` and :math:`v`.

Opposite rotations (clockwise v. counter-clockwise) produced an equivalent result.  We will come back to this point below.

Start with a vector

.. math::

    \mathbf{A} = \langle a_x, a_y \rangle
    
where :math:`a_x` and :math:`a_y` are the number of units (feet, kilometers, or microns) :math:`\mathbf{A}` extends in each direction.  An alternative notation would be to add the components in the standard coordinate system:

.. math::

    \mathbf{A} = a_x \mathbf{\hat{i}} + a_y \mathbf{\hat{j}}
    
where :math:`\mathbf{\hat{i}}` is the unit vector in the :math:`x`-direction, and :math:`\mathbf{\hat{j}}` is the unit vector in the :math:`y`-direction.

Now, let's think about how to rotate :math:`\mathbf{A}` by 90 degrees counter-clockwise to become :math:`\mathbf{A}'`.  

Drawing a dotted rectangle helps in visualizing the change.  Whatever length the :math:`x`-coordinate of :math:`\mathbf{A}` has, that same value will be the length of the :math:`y`-coordinate of the rotated vector :math:`\mathbf{A}'`.

.. image:: /figs/rotated_vec.png
   :scale: 50 %

On the other hand, **minus** the :math:`y`-coordinate of :math:`\mathbf{A}` will become the :math:`x`-coordinate of :math:`\mathbf{A}'`.

The reason for the different sign of the second term should be apparent from consideration of the figure above.

===============
Matrix notation
===============

Let's look at a particular example for this 90 degree counter-clockwise rotation.  Suppose :math:`\mathbf{A} = \langle a_x, a_y \rangle = \langle 3, 1 \rangle`.  Then :math:`\mathbf{A'} = \langle a'_x, a'_y \rangle = \langle -1, 3 \rangle`.

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

To obtain the first component :math:`a_x'` of the result (which has the value :math:`-3`), we did this multiplication:

.. math::

    a_x' = 0 \times a_x + (-1) \times a_y = - 3
    
This can be understood as a multiplication component-wise of the first row of T times the column vector :math:`\langle a_x, a_y \rangle`.  In the same way, the second component :math:`a_y'` of the result (has the value :math:`1`), obtained by this multiplication:

.. math::

    a_y' = 1 \times a_x + 0 \times a_y = 1

=====================
Matrix multiplication
=====================

The rule for matrix multiplication is as follows:

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

============
General case
============

Rotation by 90 degrees is obviously a special case.  The general case involves some angle :math:`\theta`, and I bet you can guess that the formula will involve the sine and cosine of the angle :math:`\theta`.  If we look again at the rotation matrix, I think you might also guess what the formulas are in terms of the sine and cosine of :math:`\pi/2`:

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

And if you are paying particular attention, you will see that there is a change of sign from the first example.  For this one:

.. math::
    
    T_{\theta} = 
    \begin{bmatrix}
    \cos \theta && \sin \theta \\
    -\sin \theta && \ \cos \theta
    \end{bmatrix}

The reason is that, in the second example, we rotated the coordinate system, not the vector or point.  Rotation of the coordinate system counter-clockwise is equivalent to rotating the point *clockwise*.  Hence the change of sign.
