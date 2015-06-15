.. _partial-diff:

##############################
Functions of several variables
##############################

This book is nearly all about functions of a single variable, but there are a couple of neat examples that involve functions of more than one variable, where we need to be able to differentiate.

Luckily the extension is simple to perform.  The key point is that when differentiating with respect to one variable, any other variables are treated as *constants*.

There is a lot more to say about the topic, of course, but that is all that is needed for now.

To be concrete, suppose we have a function :math:`z = f(x,y)`, for example

.. math::

    z = axy^2;  \ \ \ a = \ \text{const}

We can visualize (plot) the function as a surface in three-dimensional space, formed by connected points that satisfy the equation.  If we take the derivative with respect to :math:`x`, then :math:`y` is a constant, and we are concerned only with a cross-section of the surface parallel to the :math:`x`- and :math:`z`-axes and perpendicular to the :math:`y`-axis.

.. image:: /figs/intersect.png
   :scale: 50 %

Along this cross-section, the surface is just an ordinary curve, and the "partial derivative" determines the slope of the curve, in the usual way.

When doing partial differentiation, we use a new symbol for the derivative:  :math:`\partial`.  We write

.. math::

    \frac{\partial z}{\partial x}

and say "partial z, partial x" for the partial derivative of :math:`z` with respect to :math:`x`.  And in taking that derivative, we treat :math:`y` as a constant:

.. math::

    \frac{\partial z}{\partial x} = \frac{\partial}{\partial x} axy^2
    
    = ay^2
    
Similarly

.. math::

    \frac{\partial z}{\partial y} = \frac{\partial}{\partial y} axy^2
    
    = 2axy

That's all there is to it.