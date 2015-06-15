.. _taylor:

#############
Taylor Series
#############

Some functions that arise in applications (like physics) can be difficult to handle.  They may be hard to evaluate the value of :math:`f(x)` at :math:`x=a`, or they may be a pain to integrate.  Thus, we seek a way of constructing functions that approximate the value of a given function.  In particular, we seek polynomial functions of the form:

.. math::

    g(x) = c_0 + c_1 x + c_2 x^2 + c_3 x^3 + \dots

Suppose we start work in the region near :math:`x=0`.  There, we want to match the value of the function :math:`f(x)` at :math:`x=0` which is:

.. math::

    f(0) = c_0 + c_1 x + c_2 x^2 + c_3 x^3 + \dots
    
    f(0) = c_0

The next step is to make the tangent to the curve :math:`g(x)` equal to the tangent to the curve :math:`f(x)` at :math:`x=0`.  We do this by making the first derivatives match:

.. math::

    g'(x) = c_1 + (2)c_2 x + (3)c_3 x^2 + \dots
    
    f'(0) = c_1

We also want the curvature to be the same, so we we make the second derivatives match:

.. math::

    g''(x) = (2)c_2 + (2)(3) c_3 x + \dots
    
    f''(0) = 2 c_2

    c_2 = \frac{f''(0)}{2}

When we continue to the third derivative, notice that we pick up a factor of :math:`2 \times 3 = 3!`, so the general formula for the coefficients is

.. math::

    c_n = \frac{f^n(0)}{n!}

(where :math:`f(n)` is the nth derivative of :math:`f`), and the function :math:`g(x)` is

.. math::

    g(x) =  \sum_0^{\infty} \frac{f^n(0)}{n!} x^n

We take as many terms as we need in order to have a good approximation.

+++++++
Example
+++++++

Consider :math:`f(x) = \sin x`.  The coefficients are:

.. math::

    c_0 = f(0) = \sin 0 = 0
    
    c_1 = f'(0) = \cos 0 = 1
    
    c_2 = f''(0) = - \sin 0 = 0
    
    c_3 = f'''(0) = - \cos 0 = -1

and then it repeats.  Combining with the powers of :math:`x` we obtain

.. math::

    \sin x = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \frac{x^7}{7!}

The *small angle* approximation for :math:`\sin x` equals :math:`x`, when :math:`x` is close to :math:`0`.

Here is a comparison plot of the sine function versus various series.  The curve in purple ("plum") corresponds to the equation just above.  It matches the sine very well for an entire period of :math:`\pi`.

.. image:: /figs/taylor.png
   :scale: 50 %


The equivalent series for cosine is:

.. math::

    \cos x = 1 - \frac{x^2}{2!} + \frac{x^2}{2!} - \frac{x^2}{2!}

This approximation for :math:`x \approx 0` is called the Maclaurin series.

.. math::

    g(x) = \sum_{n=0}^{n=\infty} \frac{f^n(0)}{n!} (x)^n

The general approach for :math:`x \approx a` is the Taylor series.  Here is the formula:

.. math::

    g(x) = \sum_{n=0}^{n=\infty} \frac{f^n(a)}{n!} (x-a)^n

