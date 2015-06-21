.. _differentiable:

##############
Differentiable
##############

A function is differentiable at a point :math:`x=a` if the derivative is defined at that point, that is if this limit

.. math::

    f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}

is defined at :math:`x=a`, that is, if the limit exists.  So for example

.. math::

    f(x) = \ln x

    f'(x) = \frac{1}{x}

In the above example, :math:`f(x)` is differentiable everywhere, except at :math:`x=0`.
