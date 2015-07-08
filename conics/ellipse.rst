.. _ellipse:

#######
Ellipse
#######

The standard equation for a simple ellipse (aligned with the :math:`x`- and :math:`y`-axes) is 

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

From the formula it is easy to see that when

.. math::

    x=0
    
    y = \pm b

and similarly when 

.. math::

    y=0
    
    x = \pm a

.. image:: /figs/ellipse2.png
   :scale: 50 %

The graphic, which is from wikipedia, shows a typical ellipse.  The geometric definition of an ellipse is the set of points which has

.. math::

    PF_1 + PF_2 = \text{constant}

The sum of the distances from any point to each of the two foci is a constant.  The foci lie on the semi-major axis (the long axis of the ellipse), which here is the :math:`x`-axis.  

The formula for the focal distance (the distance :math:`f` along the :math:`x`-axis from the origin to either focus) is

.. math::

    a^2 - b^2 = f^2
    
    b^2 + f^2 = a^2

Or solving for :math:`f`:

.. math::

    f = \sqrt{a^2 - b^2}

For example, if :math:`a=5` and :math:`b=3` then :math:`f=4`, so the foci are the two points :math:`(0,-f), (0,f)`.  (Some authors switch the labels :math:`a` and :math:`b` depending on which is the major axis, but I find it confusing).

The **eccentricity** :math:`e` is equal to the ratio:

.. math::

    e = \frac{f}{a}

Here is a table of planetary eccentricities I found on the web:

.. image:: /figs/eplanets.png
   :scale: 50 %

==========
Derivation
==========

If :math:`P` (:math:`x,y`) lies to the right of the :math:`y`-axis, (:math:`x > 0`), then the distance from :math:`F_1` to :math:`P` is

.. math::
 
    \sqrt{(x + f)^2 + y^2}

and from :math:`F_2` it is

.. math::

    \sqrt{(x - f)^2 + y^2}

This sum is a constant, and equal to :math:`2a` as seen from the point :math:`P=(a,0)`

.. math::

    PF_1 + PF_2 = a - f + a + f = 2a

The relation to :math:`b` can be found from considering the point :math:`Q=(0,b)` where 

.. math::

    PF_1 + PF_2 = 2\sqrt{b^2 + f^2} = 2a

    b^2 + f^2 = a^2

Given :math:`a` and :math:`b` one can then find :math:`f` easily.

===================
Additional comments
===================

The first comment is that just as for the other quadratic formulas, one can move the center of the ellipse by including offsets

.. math::

    \frac{(x-h)^2}{a^2} + \frac{(y-k)^2}{b^2} = 1

When presented with an equation in which terms like :math:`-2xh` or :math:`-2yk` present, you need to "complete the square" to rearrange the terms as :math:`(x-h)^2` and :math:`(y-k)^2`, respectively.

Recall that if

.. math::

    Ax^2 + Bxy + Cy^2 + Dx + Ey + F =0

the "discriminant" is :math:`D = B^2 - 4AC` and if :math:`D<0`, then the equation is an ellipse.  The presence of an :math:`xy` term indicates a rotated quadratic (though it is not an ellipse if :math:`B^2 > 4AC`).

====================
Parametric equations
====================

These are simply

.. math::

    x = a \cos \theta

    y = b \sin \theta

It can be verified easily that these solve the basic equation

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

and note, for example that if :math:`\theta=\pi/4` then :math:`x = a/\sqrt{2}; \ \ y = b/\sqrt{2}`.

=======================
Equation of the ellipse
=======================

We have enough to derive the equation of the ellipse, with a moderate amount of algebra.  Recall the definition that the sum of the distances to the two foci together is a constant, equal to :math:`2a`:

.. math::

    2a = \sqrt{(x + f)^2 + y^2} + \sqrt{(x - f)^2 + y^2}

    \sqrt{(x - f)^2 + y^2} = 2a - \sqrt{(x + f)^2 + y^2}

The main problem is the square roots.  We get rid of one:

.. math::

    (x - f)^2 + y^2 = 4a^2 - 4a \sqrt{(x + f)^2 + y^2} + (x+f)^2 + y^2

    (x - f)^2 = 4a^2 - 4a \sqrt{(x + f)^2 + y^2} + (x+f)^2

do some simplification:

.. math::

    (x - f)^2 - (x + f)^2 = 4a^2 - 4a \sqrt{(x + f)^2 + y^2}
    
    - 4xf - 4a^2 = - 4a \sqrt{(x + f)^2 + y^2}
        
    \frac{xf}{a} + a = \sqrt{(x + f)^2 + y^2}

and then get rid of the other square root:

.. math::


    \frac{x^2f^2}{a^2} + 2xf + a^2 = (x + f)^2 + y^2

    \frac{x^2f^2}{a^2} + a^2 = x^2 + f^2 + y^2

Recall that :math:`f^2 = a^2 - b^2`:

.. math::

    x^2 -\frac{x^2b^2}{a^2} + a^2 = x^2 + a^2 - b^2 + y^2

    -\frac{x^2b^2}{a^2} = - b^2 + y^2

    \frac{x^2}{a^2} = 1 - \frac{y^2}{b^2}

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

Additional material about the ellipse is :ref:`here <ellipse-parametric>`.