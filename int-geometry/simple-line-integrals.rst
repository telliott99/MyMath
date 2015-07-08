.. _simple-line-integrals:

##############
Line Integrals
##############

A simple application of a line integral is to find the length of a curve.  A more sophisticated one yields the work done when moving along a curve, and there are certainly others.

The basic formula can be derived by doing algebra with differentials.  Think of a small element of the path of the curve, :math:`ds`, as a right triangle with side lengths :math:`dx` and :math:`dy`.  Then Pythagoras says that

.. math::

    ds^2 = dx^2 + dy^2

We "divide and multiply" on the right by :math:`dx^2` to give

.. math::

    ds^2 = [1 + \frac{dy^2}{dx^2}] \ dx^2

then take the square root

.. math::

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx

    ds = \sqrt{1 + (y')^2} \ dx

In many cases :math:`x` and :math:`y` will be parametric equations (functions of a parameter like :math:`t`), but they don't have to be.

Notice that even as :math:`dx` gets very small, the path element `ds` has a "rate of exchange" with it, governed by the slope.  On the other hand, when we compute Riemann sums to get the area beneath a curve, this discrepancy can be ignored, because it is very small compared to the second factor in the area, :math:`f(x)`.

=======
Example
=======

Here is one where we already know the answer:  the arc length along the boundary of the circle of radius :math:`R` in the first quadrant.  Again, the formula is

.. math::

    ds = \sqrt{1 + (\frac{dy}{dx})^2} \ dx

So we want

.. math::

    \int ds = \int_0^R  \sqrt{1 + (\frac{dy}{dx})^2} \ dx

The circle is

.. math::

    x^2 + y^2 = R^2

By implicit differentiation, we easily obtain

.. math::

    \frac{dy}{dx} = -\frac{x}{y}
    
    (\frac{dy}{dx})^2 = \frac{x^2}{y^2}

So the integral is

.. math::

    = \int_0^R  \sqrt{1 + \frac{x^2}{y^2}} \ dx

    = \int_0^R \frac{1}{y}  \sqrt{y^2 + x^2} \ dx

    = R \int_0^R \frac{1}{y}  \ dx

    = R \int_0^R \frac{1}{\sqrt{R^2-x^2}}  \ dx

This can be solved by a trig substitution:

.. math::

    x = R \sin t

    dx = R \cos t dt

    \sqrt{R^2 - x^2} = R \cos t

So we have

.. math::

    = R \int \frac{1}{R \cos t} R \cos t \ dt 
    
    = R \int dt = R t

The slightly tricky part is the limits on :math:`t`.  The lower limit was :math:`x=0`, so now we need :math:`R \sin t = 0`, so :math:`t=0`.  

And the upper limit was :math:`x=R`, so now we need :math:`R \sin t = R` so :math:`t = \pi/2`.  The integral is :math:`\pi R/2` and the whole circumference is :math:`4` times that or :math:`C = 2 \pi R`.

Alternatively, we could convert back to :math:`x`:

.. math::

    = R \sin^{-1} x

We have the bounds :math:`x = 0 \rightarrow R`, so the result is just :math:`R \pi/2`.

Another, simpler way to do this calculation is to use the parametrized circle (:math:`x = \cos \theta, y = \sin \theta`).  Go back to the original definition of the element of arc :math:`ds`:

.. math::

    ds^2 = dx^2 + dy^2

    L = \int ds = \int \sqrt{dx^2 + dy^2}

    = \int \sqrt{\cos^2 \theta + \sin^2 \theta} \ d \theta

    = \int \ d \theta

Here, we can just go all the way around the circle from :math:`\theta = 0 \Rightarrow 2 \pi`.  And for a circle of radius :math:`a` we have :math:`a \cos \theta` and :math:`a \sin \theta` which gives a factor of :math:`a^2` under the square root, yielding an extra factor of :math:`a` in the end.
