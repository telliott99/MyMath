.. _lim_x_sinx:

##############
A famous limit
##############

The fundamental result of calculus with respect to trigonometric functions depends on this limit

.. math::

    \lim_{x \rightarrow 0} \ \frac{x}{\sin x}

The ratio of the angle to its sine as the angle gets very small.  Here is a simple proof that the ratio is equal to :math:`1`.

.. image:: /figs/lim_x_over_sinx.png
   :scale: 50 %

Consider the triangle that lies entirely inside the circle.  Its base is :math:`r \cos t` and its height is :math:`r \sin t`, so its area is

.. math::

    A = \frac{1}{2} \cdot r \cos t \cdot r \sin t 
    
    = \frac{1}{2} r^2 \sin t \cos t

Consider next the segment of the circle with angle :math:`t`.  Its area is that fraction of the total angle :math:`2 \pi`, times the total area.

.. math::

    A = \frac{t}{2 \pi} \pi r^2 = \frac{1}{2} r^2 t

Finally, consider the triangle containing the dotted line.  By similar triangles, its height (that dotted line) is in the same ratio to :math:`r` (which is the base of that triangle), as sine is to cosine of the angle.  That is, its length is :math:`r \tan t` and so the area of the triangle is

.. math::

    A = \frac{1}{2} \cdot r \cdot r \tan t 
    
    =  \frac{1}{2} r^2 \ \frac{\sin t}{\cos t}

Since these areas get progressively larger *no matter how small t becomes*:

.. math::

    \frac{1}{2} r^2 \sin t \cos t < \frac{1}{2} r^2 t < \frac{1}{2} r^2 \ \frac{\sin t}{\cos t}

Now cancel :math:`r^2/2` and divide by :math:`\sin t`

.. math::

    \cos t < \frac{t}{\sin t} < \frac{1}{\cos t}

As :math:`t \rightarrow 0`, both :math:`\cos t` and :math:`1/\cos t` approach the same limit, :math:`1`.  Therefore the ratio gets squeezed, and it approaches the same limit as well.  Therefore:

.. math::

    \lim_{x \rightarrow 0} \ \frac{x}{\sin x} = 1