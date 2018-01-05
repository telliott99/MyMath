.. _euler-addition:

###################
Starting from Euler
###################

A very quick and simple derivation of formulas for the sine or cosine of the sum and difference of two angles depends on Euler's equation, which you may have seen before, and we will discuss more :ref:`here <euler-eqn>`.

.. math::

    e^{i\theta} = \cos \theta + i \sin \theta

The right-hand side seems clear enough---this is a point in the "complex plane", indexed by the cosine and sine of an angle :math:`\theta` formed by a ray to the point from the origin, and the horizontal (:math:`x`-axis, the real numbers).

Algebra of complex numbers can be done using :math:`a + bi` formulation, or equivalently using :math:`r e^{i\theta}` (:ref:`here <complex>`) polar coordinates.

Without worrying too much yet about how the formula works, let's just use it.

We substitute :math:`s + t` for :math:`\theta`:

.. math::

    e^{i(s+t)} = \cos (s+t) + i \sin (s+t)

But by the standard rules for exponents

.. math::

    e^{i(s+t)} = e^{is+it} = e^{is} e^{it}
    
    = ( \cos s + i \sin s ) ( \cos t + i \sin t )

Just multiply out:

.. math::

    = \cos s \cos t + i \cos s \sin t + i \sin s \cos t - \sin s \sin t
    
    = \cos s \cos t - \sin s \sin t + i (\sin s \cos t + \cos s \sin t)
    
The cool thing about this is that for two complex numbers to be equal, *both the real and the imaginary parts must be equal*.  From this:

.. math::
    
    \cos (s+t) + i \sin (s+t) = \cos s \cos t - \sin s \sin t + i (\sin s \cos t + \cos s \sin t)

We get *two identities from one formula* !!

.. math::

    \cos (s+t) = \cos s \cos t - \sin s \sin t

    \sin (s+t) = \sin s \cos t + \sin t \cos

I think this is by far the easiest and best way to reconstruct the addition formulas.