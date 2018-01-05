.. _lim_x_sinx:

##############
A famous limit
##############

The fundamental result of calculus with respect to trigonometric functions depends on this limit

.. math::

    \lim_{x \rightarrow 0} \ \frac{x}{\sin x}

The limit of the ratio of the angle to its sine as the angle gets very small is equal to :math:`1`.  One way to explore this is to use a plotting application:

.. image:: /figs/sinx_over_x.png
   :scale: 50 %

or a calculator such as that embedded in Python

>>> for i in range(1,100):
...     f = 1.0/i
...     print i, sin(f)/f
... 
1 0.841470984808
..
97 0.999982286557
98 0.99998264621
99 0.999982995019
>>>

but these are (to be honest) cheating because when they calculate the sine of the angle they use a shortcut based on calculus.

Here is an actual proof that the ratio is equal to :math:`1`.

.. image:: /figs/lim_x_over_sinx.png
   :scale: 50 %

Consider the right triangle with radius :math:`r` (the one that lies entirely inside the circle).  Its base is :math:`r \cos t` and its height is :math:`r \sin t`, so its area is

.. math::

    A = \frac{1}{2} \cdot r \cos t \cdot r \sin t 
    
    = \frac{1}{2} r^2 \sin t \cos t

Consider next the sector of the circle (piece shaped like a slice of pie) containing the same angle, :math:`t`.  Recall that :math:`t` is the length of the portion of the circumference along this sector (if :math:`t` is measured in radians).  If the circle is not a unit circle, then multiply by the radius.

The area of the sector could then be approximated as a triangle with base :math:`r \theta` and height :math:`r`. 

Alternatively, consider that :math:`t` is some fraction of the total angular measure of the circle, namely :math:`t/2 \pi`, and we multiply by the total area of the circle to get the area of the sector:

.. math::

    A = \frac{t}{2 \pi} \pi r^2 = \frac{1}{2} r^2 t

It's the same answer.

Finally, consider the right triangle containing the dotted line, whose base has length :math:`r`.  Because it is a similar triangle with the first one, its height (that dotted line) is in the same ratio to :math:`r`, the base of the triangle, as :math:`\sin t` is to :math:`\cos t`.  Thus, its length is :math:`r \tan t` and so the area of this triangle is

.. math::

    A = \frac{1}{2} \cdot r \cdot r \tan t 
    
    =  \frac{1}{2} r^2 \ \frac{\sin t}{\cos t}

Since the first triangle is smaller than the sector, and the sector is smaller than the second triangle, *no matter how small t becomes*:

.. math::

    \frac{1}{2} r^2 \sin t \cos t < \frac{1}{2} r^2 t < \frac{1}{2} r^2 \ \frac{\sin t}{\cos t}

Now cancel :math:`r^2/2`

.. math::

    \sin t \cos t < t < \frac{\sin t}{\cos t}

and divide by :math:`\sin t`

.. math::

    \cos t < \frac{t}{\sin t} < \frac{1}{\cos t}

As :math:`t \rightarrow 0`, both :math:`\cos t` and :math:`1/\cos t` approach the same limit, :math:`1`.  Therefore the ratio gets squeezed, and it approaches the same limit as well

Therefore:

.. math::

    \lim_{x \rightarrow 0} \ \frac{x}{\sin x} = 1