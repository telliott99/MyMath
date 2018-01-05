.. _rotate-alt:

###########################
Rotation:  alternate method
###########################

Here is a second derivation which differs from the one in the main text because we are rotating not the vector but the coordinate system.  We want to transform the coordinates of the point :math:`P` (blue dot) from the familiar :math:`x,y`-coordinate system to a new system with rotated axes :math:`u,v`.

.. image:: /figs/min_rotation2.png
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

The reason is that here we rotated the coordinate system, not the vector or point.  Rotation of the coordinate system counter-clockwise is equivalent to rotating the point *clockwise*.  Hence the change of sign.

++++++++++++++++++++
Further observations
++++++++++++++++++++

In trying to derive the formula from scratch, the picture of the geometry is tricky to remember, in my experience.

The first three steps are pretty obvious:

- Draw a perpendicular from :math:`P` to the :math:`x`-axis
- Draw a perpendicular from :math:`P` to the :math:`u`-axis
- Label the second angle that is equal to :math:`t` or :math:`\theta`

.. image:: /figs/min_rotation2.png
       :scale: 25%

Now, draw the rectangle that makes everything clear:

- Draw a line from :math:`(x,0)` up and perpendicular to the :math:`u`-axis
- Label the point where it divides the :math:`u`-axis into two segments
- Draw the opposing side as an extension down
- Draw in the fourth side of the rectangle at the bottom
- Possibly, draw in the jagged path

Given the right picture, the rest is obvious.

Look for the four relationships: 

- :math:`x \sin t`
- :math:`x \cos t`
- :math:`y \sin t`
- :math:`y \cos t`

Notice that 

.. math::

    x^2 + y^2 = r^2

and this must be also true of :math:`u^2 + v^2`:

.. math::
 
    u^2 = (x \cos t + y \sin t)^2
    
        = x^2 \cos^2 t + 2 x \cos t \ y \sin t + y^2 \sin^2 t

and

.. math::

    v^2 = (x \sin t - y \cos t)^2
    
    = x^2 \sin^2 t - 2 x \sin t y \cos t + y^2 \cos^2 t

Notice the cancellation of :math:`2 x \cos t \ y \sin t` and the terms with :math:`\sin^2 t + \cos^2 t` give us exactly what we need.

A second test is that if :math:`T` is the matrix for rotation by :math:`\theta` degrees clockwise, and :math:`T'` is for counter-clockwise, then :math:`T \times T' = I` (the identity matrix), always.  Also, two sequential applications of :math:`T_{90}` give :math:`-I`, and four give :math:`+I`.

Finally, the formulas for sine and cosine of addition of angles follow from these, as well.