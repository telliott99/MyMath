.. _parabola-polar:

#################################
Other conics in polar coordinates
#################################

When converting between polar coordinates and Cartesian coordinates, we will use the familiar identities:

.. math::

    x = r \cos t
    
    y = r \sin t
    
    r = x^2 + y^2
    
    t = \tan^{-1}(\frac{y}{x})
    
======
Circle
======

A circle with vertex at :math:`(a,0)` and radius :math:`a`:

.. math::

    (x-a)^2 + y^2 = a^2
    
    x^2 + y^2 - 2ax = 0

    r^2 - 2ar \cos t = 0
        
    r = 2a \cos t

either that, or :math:`r = 0` is also a solution for any angle :math:`t`.

A circle of radius :math:`a` centered at :math:`(0,a)` is

.. math::

    r = 2a \sin t
    
and the combination

.. math::

    r = 2 (\sin t + \cos t)
    
is a circle of radius :math:`1` centered at :math:`(\sqrt{2}, \sqrt{2})` since the maximum value for :math:`r` occurs when :math:`t = \pi/4` and :math:`r = 2 \sqrt{2}`.  The radius of the *circle* is half that.
    
=============
Straight line
=============

These are straight lines:

.. math::

    r = \frac{a}{\cos t}
    
is the vertical line :math:`x = a`, and

.. math::

    r = \frac{a}{\sin t + \cos t}

is the line with equation

.. math::

    x + y = a
    
    y = -x + a

========
Parabola
========

In Cartesian or :math:`x,y`-coordinates the basic equation is:

.. math::

    y = ax^2

where :math:`a` is the "shape factor".  However, for polar equations it seems more traditional to turn the parabola so that we have something like :math:`x = ay^2`.  The reason is that it preserves the connection to the ellipse that we did previously, where the long axis is the :math:`x`-axis.  

Here is a figure I found on the web

http://laurashears.info/math122/unit4/polarAndParamFormsOfParabola/

.. image:: /figs/parabola-polar.png
   :scale: 50 %

The focus of the parabola is placed at the origin, so the vertex is shifted to the left by a distance :math:`p`, which I will call :math:`c` in keeping with the notation we used for the ellipse.

The geometric definition of the parabola is the set of points that are equidistant from the directrix (which is one focal-length from the vertex), and the focus.  This distance is labeled as :math:`r` in the diagram.  It's pretty clear from this constraint that

.. math::

    r = 2c + r \cos \theta

Rearranging:

.. math::

    r = \frac{2c}{1 - \cos \theta}

switching to our notation:

.. math::

    r = \frac{2c}{1 - \cos t}

Converting back to Cartesian coordinates is just a matter of 

.. math::

    r = 2c + x
    
    r^2 = 4p^2 + 4cx + x^2
    
    x^2 + y^2 = 4c^2 + 4px + x^2
    
    y^2 = 4px + 4c^2
    
    \frac{1}{4c} y^2 = x + p

This is a shifted parabola (the vertex is at :math:`x=-c, y = 0`).  The shape factor is

.. math::

    a = \frac{1}{4c}
    
which is consistent with what we found studying parabolas in Cartesian coordinates.

Compare the parabola:

.. math::

    r = \frac{2c}{1 - \cos t}

with the ellipse:

.. math::

    r = \frac{c}{1 - e \cos t}
    
For the ellipse, :math:`e` must be less than :math:`1` otherwise :math:`r` can become negative for some values of :math:`t`, and we wouldn't have an ellipse.


    