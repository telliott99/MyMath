.. _rotate-vectors:

#######################
Vectors and coordinates
#######################

In this section we will take a look at the formulas for rotation of vectors and coordinate systems in two dimensions.

The first observation is that these two different types of rotation (of vectors and coordinates) are in a sense, opposites.

.. image:: /figs/rotate_vec_coord.png
   :scale: 50 %

In the left panel, vector :math:`\mathbf{A}` is rotated *clockwise* by 30 degrees (:math:`\pi/6`) to give vector :math:`\mathbf{A}'`.  In the right hand panel, instead, the coordinate system has been rotated *counter-clockwise* by 30 degrees to give new axes :math:`u` and :math:`v`.

After both operations we end up with the same relationship between vector and coordinate system.  The projection of :math:`\mathbf{A}'` onto the :math:`x`-axis in the left panel is equal in length to the projection of vector :math:`\mathbf{A}` onto the :math:`u`-axis in the right panel, and likewise for :math:`y` and :math:`v`.

Clockwise rotation of a vector produces an equivalent result to counter-clockwise rotation of the coordinate system.  Similarly, counter-clockwise rotation of a vector produces an equivalent result to clockwise rotation of the coordinate system.  We will come back to this point below.

###################
Rotation of Vectors
###################

Start with a vector

.. math::

    \mathbf{A} = \langle a_x, a_y \rangle
    
where :math:`a_x` and :math:`a_y` refer to the number of units (kilometers, feet, or perhaps microns) that :math:`\mathbf{A}` extends in each direction.  An alternative notation is to add the components in the standard coordinate system:

.. math::

    \mathbf{A} = a_x \mathbf{\hat{i}} + a_y \mathbf{\hat{j}}
    
where :math:`\mathbf{\hat{i}}` is the unit vector (vector of length one) in the :math:`x`-direction, and :math:`\mathbf{\hat{j}}` is the unit vector in the :math:`y`-direction.

Now, let's think about how to rotate :math:`\mathbf{A}` by 90 degrees counter-clockwise to become :math:`\mathbf{A}'`.  

Drawing a dotted rectangle helps in visualizing the change.  Whatever length the :math:`x`-coordinate of :math:`\mathbf{A}` has, that same value will be the :math:`y`-coordinate of the rotated vector :math:`\mathbf{A}'`.

.. image:: /figs/rotated_vec.png
   :scale: 50 %

On the other hand, **minus** the :math:`y`-coordinate of :math:`\mathbf{A}` will become the :math:`x`-coordinate of :math:`\mathbf{A}'`:  :math:`a_y \rightarrow a_x '` changes sign.

The reason for the different sign of the second term should be apparent from consideration of the figure.

In contrast, suppose we start with :math:`\mathbf{A'}` and rotate it clockwise 90 degrees to become :math:`\mathbf{A}`.  In this transformation it is :math:`a_x ' \rightarrow a_y` that comes with a change of sign.  :math:`a_y ' \rightarrow a_x` comes without a sign change.

==========
Derivation
==========

This material assumes a basic understanding of vector notation and matrix multiplication.  For an introduction or brief review, see :ref:`here <vectors-matrices>`.

A simple way to get the rotation formulas is to think about how to rotate the unit vectors by an angle :math:`\theta` counter-clockwise.

Start with :math:`\mathbf{\hat{i}} = \langle 1,0 \rangle`.  After rotation, the vector should be just as long as before, but rotated through an angle :math:`\theta` counter-clockwise.  Thus, its projection on the :math:`x`-axis (its :math:`x` "component") will be simply :math:`\cos \theta`, and the :math:`y`-component will be :math:`\sin \theta`.

The question is then, what values for :math:`a` and :math:`c` give a matrix that will multiply :math:`\mathbf{\hat{i}} = \langle 1,0 \rangle` to give the result we seek?

.. math::

    \begin{bmatrix}  
    a & b  \\  
    c & d  
    \end{bmatrix}
    \begin{bmatrix}  
    1  \\  
    0  
    \end{bmatrix}
    =
    \begin{bmatrix}  
    \cos\  \theta  \\  
    \sin\  \theta  
    \end{bmatrix}

From this requirement, we see that :math:`a = \cos \theta` and :math:`c = \sin \theta`.

Similarly, what values for :math:`b` and :math:`d` give a matrix which will multiply :math:`\mathbf{j}` to give the vector :math:`\langle -\sin \theta, \cos \theta \rangle`.

From this, we see that :math:`b = - \sin \theta` and :math:`d = \cos \theta`.

The combined answers give:

.. math::

    \begin{bmatrix}  
    \cos \  \theta  & -\sin \  \theta \\  
    \sin \  \theta  & \ \ \cos \  \theta
    \end{bmatrix}

The trick is that if we rotate every vector counter-clockwise by an angle :math:`\theta`, that is equivalent to rotating the coordinates by the same angle but in the opposite direction, *clockwise*.  Label the matrix above :math:`R{+}`

.. math::

    R{+} =
    \begin{bmatrix}  
    \cos \  \theta  & -\sin \  \theta \\  
    \sin \  \theta  & \ \ \cos \  \theta
    \end{bmatrix}

with the understanding that it rotates *vectors* in the CCW direction, with :math:`\theta` increasing.  Its inverse :math:`R{-}` rotates vectors in the direction of decreasing :math:`\theta`, and :math:`R{-} \times R{+} = R{+} \times R{-} = I`, the identity matrix.  Thus

.. math::

    R{-} =
    \begin{bmatrix}  
    \ \ \cos \  \theta  & \sin \  \theta \\  
    -\sin \  \theta  & \cos \  \theta
    \end{bmatrix}
    
and 

.. math::

    \begin{bmatrix}  
    \cos \  \theta  & -\sin \  \theta \\  
    \sin \  \theta  & \ \ \cos \  \theta
    \end{bmatrix}
    \times
    \begin{bmatrix}  
    \ \ \cos \  \theta  & \sin \  \theta \\  
    -\sin \  \theta  & \cos \  \theta
    \end{bmatrix}
    
    =
    \begin{bmatrix}  
    \cos^2  \theta + \sin^2 \theta  & \cos \theta \sin \theta -\sin \theta \cos \theta \\  
    \sin \theta \cos \theta - \cos \theta \sin \theta  & \sin^2 \theta + \cos^2 \theta
    \end{bmatrix}
    
    =
    \begin{bmatrix}  
    1  & 0 \\  
    0  & 1
    \end{bmatrix}

which is the identity matrix, :math:`\mathbf{I}`.  

:math:`\mathbf{I} \times \mathbf{v} = \mathbf{v}` for any vector  :math:`\mathbf{v}`.

As shown above, it is easily verified that the products on the diagonal are equal to :math:`1` and those off the diagonal are equal to :math:`0`.

