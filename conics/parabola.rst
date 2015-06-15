.. _parabola:

########
Parabola
########

This quick write-up is about the parabola.  Let's start by considering parabolas in standard orientation, i.e. that open up and have their axis of symmetry pointed straight up and down.

A parabola in this standard orientation whose vertex is located at the origin can be described by the very simple equation

.. math::

    y = a x^2

Notice that :math:`(x=0,y=0)` is a solution to this equation.

All parabolas contain a term with something (perhaps :math:`1`) multiplied by :math:`x^2`.  If the power of :math:`x` isn't :math:`2`, the figure isn't a parabola.  

There are three operations that can be used to transform the basic parabola :math:`y=x^2` into any other parabola. 

First, we can multiply by a constant, usually designated :math:`a`.  :math:`a` is called the "shape parameter".  You might think of :math:`a` as a kind of magnifying glass for the y-dimension.  

Second, we can translate (move) the parabola from the origin to a new position with its vertex at :math:`P = (h,k)`.  And third, we can rotate the parabola, for example so that its axis of symmetry lies along the line :math:`y = x`.

You've certainly seen this standard equation before

.. math::

    y = ax^2 + bx + c

This is the equation for a parabola with the vertex at a point other than the origin.

For two parabolas that have the same shape but differ only by translation, the :math:`a` terms in these two equations are the same.  The difference---the extra terms

.. math::

    bx + c

describe the movement, as we'll see below.

======
Simple
======

Let's start by thinking about the simplest parabola

.. math::

    y = x^2


.. image:: /figs/para1.png
   :scale: 50 %

where, again, the standard coefficients are usually labeled as

.. math::

    y = ax^2 + bx + c

In this example (:math:`y=x^2`)

.. math::

    a=1 \ \ \ b=0 \ \ \ c=0

The parabola points up.  As :math:`x` gets large, :math:`y` gets very large.

Notice that :math:`x^2` is always positive or zero; hence the minimum value of :math:`y` is :math:`0`, and the corresponding :math:`x` is also :math:`0`, and thus the vertex, the point at which :math:`y` is a minimum, is at :math:`(0,0)`.

A general way of calculating the :math:`x` coordinate of the vertex, when it's not at :math:`x=0`, is to use the equation

.. math::

    x = -\frac{b}{2a}

In this case 

.. math::

    x = -\frac{0}{2} = 0

The above equation can be derived from calculus but also by algebraic manipulation, as we'll see below.

Let's next consider two things we might do to this parabola to change it:  one is to modify the shape to rise either more quickly or more slowly, and the second is to change the location of the vertex.

As we said, the coefficient :math:`a` is called the "shape parameter".  The larger the magnitude of :math:`a`, the steeper the curve, and if :math:`a` is negative, the parabola opens downward. 

Keeping the origin at :math:`(0,0)`, with

.. math::

    a = 1, \ \  y = ax^2 = x^2

so 

.. math::

    x = \pm 1, y=(\pm 1)^2 = 1

    x = \pm 2, y=(\pm 2)^2 = 4

whereas if :math:`a=2` then

.. math::

    y = 2x^2

    x = \pm 1, y=2(\pm 1)^2 = 2

    x = \pm 2, y=2(\pm 2)^2 = 8

===========
Translation
===========

Suppose the vertex of the parabola :math:`y=x^2` is at :math:`P=(2,1)`.  

.. image:: /figs/para1b.png
   :scale: 50 %

The letters :math:`h` and :math:`k` are traditionally used for these values, which are constants for any particular parabola.  For example, here :math:`h=2` and :math:`k=1`, given the vertex at :math:`(2,1)`.

We write the equation of this parabola

.. math::

    (y-k) = a(x-h)^2  

It may seem counterintuitive that the equation has minus signs (i.e. :math:`y-k` *and* :math:`x-h`).

.. math::

    (y-1) = (x-2)^2

Even though the equation has :math:`(y-k)` the y-value at the vertex is :math:`k`.

One way to remember see is to put the :math:`k` on the other side

.. math::

    y = (x-h)^2 + k

Now it's clear that for positive :math:`k`, every :math:`y` is shifted *up* by :math:`k` units.

If we multiply this out (using :math:`a` to be completely general) we obtain

.. math::

    y = a(x-h)^2 + k

    y = ax^2 - 2axh + ah^2 + k

So, comparing the two forms 

.. math::

    y = ax^2 + bx + c

    y = ax^2 - 2axh + ah^2 + k

We see that the coefficient of the :math:`x` term is :math:`-2ah`, so that :math:`b` is

.. math::

    b = -2ah

    h = -\frac{b}{2a}

This is the equation we used above in finding the vertex.  If we know :math:`a` and :math:`b` we can calculate :math:`h`, obtaining the :math:`x`-value at the vertex.  Furthermore, from the above result

.. math::

    c = ah^2 + k

    k = c - ah^2 = c - \frac{b^2}{4a}

or alternatively, just plug :math:`x=h=-b/2a` into the original equation.

When we're given an equation in the form :math:`y = ax^2 + bx + c` and asked to find the vertex :math:`(h,k)`, this is how it's done.

Since the shape factor :math:`a` is independent of :math:`h` and :math:`k`, most problems with parabolas can be considered using the version with its vertex at the origin, without loss of generality.

=====
Roots
=====

The roots of the equation are the points where :math:`y = 0` so that

.. math::

    y = 0 = ax^2 + bx + c

You can solve this either by factoring (in favorable cases) or by using the quadratic formula

.. math::

    x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}

Also, I'm sure you know that if the parabola just touches the :math:`x`-axis then the discriminant :math:`D = b^2 - 4ac = 0`, whereas if the parabola does not cross the x-axis then there are no (real) roots and :math:`D<0`.

=========
Quadratic
=========

It's not too hard to derive the quadratic equation, so I think we should take a crack at it.  We will "complete the square."  First rearrange

.. math::

    y = ax^2 + bx + c

    \frac{(y-c)}{a} = x^2 + \frac{bx}{a}

The crucial step is to observe that if we add the correct amount to the right-hand side, it can be factored

.. math::

    x^2 + \frac{bx}{a} + (\frac{b}{2a})^2 = (x + \frac{b}{2a})(x + \frac{b}{2a}) = (x + \frac{b}{2a})^2

Of course, to maintain the equality we must add the same term to the left-hand side

.. math::

    \frac{(y-c)}{a} + (\frac{b}{2a})^2
    
    \frac{1}{a} (y - c + \frac{b^2}{4a} )

Combining the two results

.. math::

    \frac{1}{a} (y - c + \frac{b^2}{4a} ) = (x + \frac{b}{2a})^2

    y-c + \frac{b^2}{4a} = a(x + \frac{b}{2a})^2

You may recognize :math:`h` and :math:`k` in this completed square (or rather :math:`-h` and :math:`-k`), but if not, take a moment to go back and compare with the equations we had before.  

Now, the roots are just the points when :math:`y=0` and so

.. math::

    -c + \frac{b^2}{4a} = a(x + \frac{b}{2a})^2

    \frac{-4ac+b^2}{4a} = a(x + \frac{b}{2a})^2

    \frac{b^2-4ac}{4a^2} = (x + \frac{b}{2a})^2

    \pm \frac{\sqrt{b^2-4ac}}{2a} = x + \frac{b}{2a}

    x = \frac{-b \pm \sqrt{b^2-4ac}}{2a}

which is the quadratic equation.

Additional material about the parabola is :ref:`here <parabola-more>`.