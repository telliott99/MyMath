.. _cubics:

######
Cubics
######

Among the applications of complex numbers that are often cited is their use in solving cubic equations.  I find the procedures for solving cubics difficult to grasp, but I discovered another approach that makes sense to me, building up to cubics from quadratics.  So let's start with

.. math::

    f(x) = ax^2 + bx + c

As you know, the graph of this function is a parabola, pointing up or down depending on the sign of :math:`a`.  It's symmetric about the vertex, which can be found in various ways, but using calculus, it is the place where the slope is equal to zero

.. math::

    2ax + b = 0

    x = - \frac{b}{2a}

    y = a(- \frac{b}{2a})^2 + b(- \frac{b}{2a}) + c

    y = \frac{b^2}{4a} - \frac{b^2}{2a} + c = - \frac{b^2}{4a} + c

Now, if the sign of the term :math:`ax^2` is positive and :math:`y < 0` at the vertex, then the parabola opens up and the vertex is below the :math:`x`-axis and there will be two real roots.  There are two places where :math:`y=0` and the graph crosses the :math:`x`-axis.  If :math:`y=0` at the vertex, then there is a single real root, that is repeated.  And if :math:`a < 0` and :math:`y` is above the :math:`x`-axis, there are no real roots.

We obtain the quadratic equation by completing the square.

.. math::

    y = ax^2 + bx + c

When is :math:`y=0`?

.. math::

    0 = ax^2 + bx + c

    -\frac{c}{a} = x^2 + \frac{b}{a}x

    -\frac{c}{a} + \frac{b^2}{4a^2} = (x^2 + \frac{b}{a}x + \frac{b^2}{4a^2})

    -\frac{c}{a} + \frac{b^2}{4a^2} = (x + \frac{b}{2a})^2

    -4ac + b^2 = 4a^2(x + \frac{b}{2a})^2

    \sqrt{b^2 - 4ac} = 2ax + b

    x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}

As an aside, if :math:`a=1`, then this is the same as

.. math::

    x = \frac{b}{2} \pm \sqrt{(\frac{b}{2})^2 - c}

and of course, we can always divide the above equation by :math:`a` to achieve this, changing the coefficients :math:`b,c` to :math:`b',c'`.

The term :math:`b^2-4ac` in the first version is called the discriminant, :math:`D`.  If :math:`D<0` there are no real solutions, but we can get two complex solutions which have the form

.. math::

    x = p \pm i q

To see why this is so, suppose :math:`b^2 < 4ac`.  Factor out :math:`-1` to obtain :math:`(-1)(b^2 - 4ac)`.  Then the factor of :math:`-1` can come out as :math:`i` and for the square root part we have :math:`\pm i \sqrt{4ac - b^2}`.

These two solutions :math:`x = p \pm i q` are complex conjugates, so that

.. math::

    (p + iq)(p - iq) = p^2 + q^2

On the other hand, if :math:`b^2 = 4ac`, there is only a single solution yielding :math:`y=0` and notice that from above, the :math:`y`-value of the vertex of the parabola is 

.. math::

    y = - \frac{b^2}{4a} + c

    0 = - \frac{b^2}{4a} + c

    b^2 = 4ac

and then :math:`D` must be equal to zero.

Finally, if :math:`D>0`, there are two real solutions.

======
Cubics
======

What about cubics?  Well, any cubic has an :math:`x^3` in it.  That means that as :math:`x` gets large and positive :math:`f(x)` is also large and positive, while if :math:`x` is large and negative, :math:`f(x)` is large and negative. 

Consequently, the graph must cross the :math:`x`-axis at least once, and so there must be at least one real root.  

When we are building a cubic from a quadratic, no matter what the quadratic, the last step must be to multiply by :math:`(x-r)`, where :math:`r` is real.

So in other words, these are the roots of any cubic

.. math::

    (x-r)(x + \sqrt{D})(x - \sqrt{D})

if :math:`D<0` then the latter two factors are complex conjugates.  They must be, so that their product gives a completely real quadratic.  If :math:`D=0` then we just have

.. math::

    (x-r)x^2

This has three roots, at :math:`x=0` (repeated) and at :math:`x=r`.  It turns out that the graph does not cross the :math:`x`-axis at :math:`x=0`, because the first derivative

.. math::

    2x

is equal to zero at :math:`x=0`, it is a local maximum or local minimum.
