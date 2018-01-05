.. _polar-intro:

#################
Polar Coordinates
#################

In standard polar coordinates points are plotted by distance from the origin, :math:`r`, as well as the angle :math:`\theta` that this ray makes with the positive :math:`x`-axis.  Converting from :math:`x,y` to :math:`r, \theta` is straightforward:

.. math::

    x = r \cos \theta, \ \ \ \cos \theta = \frac{x}{r}

    y = r \sin \theta, \ \ \ \sin \theta = \frac{y}{r}

To go the other way, use Pythagoras to write 

.. math::

    x^2 + y^2 = r^2
    
    r = \sqrt{x^2 + y^2}

    \theta = \tan^{-1} (\frac{y}{x}), \ \ x \ne 0

In polar coordinates, as in Cartesian (:math:`xy`) coordinates, the equation of a circle depends on whether it is at the origin.  If it is at the origin, then something like

.. math::

    r = 3

defines the graph.  But if it's translated away the origin, then the equations are of the form:

.. math::

    r = a \cos \theta + b \sin \theta

For example, 

.. math::

    r = 3 \sin \theta

is a circle centered at :math:`x = 0, y = 3/2`, with a radius of :math:`3/2` (it passes through the origin and the point :math:`(x=0,y=3)`.

while

.. math::

    r = \sin \theta + \cos \theta

is a circle centered at  :math:`x = 1/2, y = 1/2` which passes through the origin and has radius :math:`1/\sqrt{2}`.

Let's see if we can manipulate these equations to go back to Cartesian coordinates.

+++++++
Example
+++++++

.. math::

    r = 3 \sin \theta

    y = r \sin \theta

    \sin \theta = \frac{y}{r}

    r = \frac{3y}{r}

    r^2 = 3y = x^2 + y^2

complete the square:

.. math::

    x^2 + y^2 -3y + \frac{3}{2} =  \frac{3}{2}

    x^2 + (y - \frac{3}{2})^2 = (\sqrt{\frac{3}{2}})^2

+++++++
Example
+++++++

.. math::

    r = \sin \theta + \cos \theta

    r = \frac{y}{r} + \frac{x}{r}

    r^2 = x + y = x^2 + y^2

    x^2 - x + \frac{1}{4} + y^2 - y + \frac{1}{4} = \frac{1}{2}

    (x - \frac{1}{2})^2 + (y - \frac{1}{2})^2 = (\frac{1}{\sqrt{2}})^2

One can also write the equations for other conic sections in polar coordinates.

================
General solution
================

.. math::

    r = a \sin \theta + b \cos \theta
    
    = a \frac{y}{r} + b \frac{x}{r}

So 

.. math::

    r^2 = ay + bx = x^2 + y^2
    
We will complete the square for both :math:`x` and :math:`y`:

.. math::

    x^2 - bx + y^2 - ay = 0
    
    x^2 - bx + \frac{b^2}{4} + y^2 - ay + \frac{a^2}{4} = \frac{a^2 + b^2}{4}
    
    (x - \frac{b}{2})^2 + (y - \frac{a}{2})^2 = (\frac{\sqrt{a^2 + b^2}}{2})^2
    
This is a circle centered at :math:`(b/2,a/2)` with radius equal to :math:`\sqrt{a^2 + b^2}/2`.  Comparing with the previous problem, we had :math:`a = b = 1` so :math:`r = \sqrt{2}/2 = 1/\sqrt{2}`.

+++++++
Example
+++++++

The following is a parabola:

.. math::

    r = \frac{2}{1 + \sin \theta}

Plot it to see.

.. image:: /figs/polar-parabola.png
   :scale: 50 %

Or just do this:

.. math::

    r  + r \sin \theta = 2

    \frac{y}{r} = \sin \theta

    r + y = 2

    r^2 = (2-y)^2  = x^2 + y^2

    4 - 4y + y^2 = x^2 + y^2

    4 - 4y = x^2
    
    y = -\frac{1}{4} x^2  + 1

+++++++
Example
+++++++

.. math::

    r = \frac{c}{(a \cos t + b \sin t)}

is the equation of a line.  To see this, substitute :math:`x = r \cos t` and :math:`y = r \sin t`:

.. math::

    r = \frac{c}{(a(x/r) + b(y/r))}
    
    r = \frac{rc}{ax + by}

    c = ax + by
    
    y = -\frac{a}{b} x + \frac{c}{b}

This image has some examples from *The Calculus Lifesaver*.

.. image:: /figs/polarex.png
   :scale: 50 %


This reference

http://www.edmath.org/MATtours/ellipses/ellipses1.07.3.html

finds the equation for an ellipse (centered at the origin).

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1
    
Do the standard substitution:

.. math::

    x = r \cos \theta 
    
    y = r \sin \theta
    
    \frac{r^2 \cos^2 \theta}{a^2} + \frac{r^2 \sin^2 \theta}{b^2} = 1
    
    b^2 r^2 \cos^2 \theta + a^2 r^2 \sin^2 \theta = a^2 b^2
    
Write :math:`\sin^2` in terms of the cosine squared:

.. math::

    b^2 r^2 \cos^2 \theta + a^2 r^2 (1 - \cos^2 \theta) = a^2 b^2
    
    r^2 \ [ \ (b^2 - a^2) \cos^2 \theta + a^2 \ ] \ = a^2 b^2

Recall that :math:`c^2 = a^2 - b^2` so:

.. math::

    r^2 \ [ \ a^2 - c^2 \cos^2 \theta \ ] \ = a^2 b^2
    
    r = \frac{ab}{\sqrt{a^2 -c^2 \cos^2 \theta}}

The equation can be simplified by putting one focus of the ellipse at the origin.  Then they obtain:

.. math::

    r = \frac{b^2}{a - c \cos \theta}

=========================
General solution, Varberg
=========================

According to Varberg

For a conic of eccentricity :math:`e`, with its focus at the origin and the directrix is the line :math:`x = -d`, then, the polar equation is:

.. math::

    r = \frac{ed}{1- e \cos t}

and the graph of 

.. math::

    r = a \cos nt
    
    r = a \sin nt

is a :math:`2n`-petaled rose if :math:`n` is even, or an :math:`n`-petaled rose if :math:`n` is odd (traversed twice)

