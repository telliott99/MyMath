.. _series-intro:

##############################
Infinite Series:  introduction
##############################

================
Geometric series
================

According to Strang, the most important series of all is the *geometric* series:

.. math::

    1 + x + x^2 + x^3 + \dots = \sum_{n=0}^{\infty} x^n

Probably the most well-known example has :math:`x = 1/2`:

.. math::

    1 + \frac{1}{2} + \frac{1}{4} + \frac{1}{8} + \dots

Although the number of terms in this series is infinite, the sum is finite.  Here is a "visual proof":

.. image:: /figs/series1.png
   :scale: 50 %

In this figure, we see that (ignoring the first term, :math:`1`)---each subsequent step takes us exactly one-half of the remaining distance to :math:`1`.  So the sum of the series written above is equal to :math:`1 + 1 = 2`.

On the other hand, clearly when :math:`x=1`, the series is not finite:

.. math::

    1 + x + x^2 + x^3 + \dots
    
    1 + 1 + 1 + 1 +  \dots
    
And when :math:`x = -1`, the series oscillates:

.. math::

    1 - 1 + 1 - 1 +  \dots

Analytical solution of the geometric series involves consideration of the partial sum :math:`S_n`:

.. math::

    S_n = 1 + x + x^2 + x^3 + \dots + x^n

Observe that multiplication by :math:`1-x` produces a "telescoping sum" so that

.. math::

    (1 - x) S_n 
    
    = S_n - x S_n
    
    =  1 + x + x^2 \dots + x^n - x - x^2 \dots - x^n - x^{n+1}

    = 1 - x^{n+1}

So

.. math::

    S_n = \frac{1 - x^{n+1}}{1-x}
    
    = \frac{1}{1-x} - \frac{x^{n+1}}{1-x}

To evaluate the infinite series, we ask what this limit is

.. math::

    \lim_{n \rightarrow \infty} \frac{x^{n+1}}{1-x}

If 

.. math::

    x^{n+1} \rightarrow 0 \ \ \text{as} \ \ n \rightarrow \infty

then the series converges.  This happens when :math:`|x| < 1` and we call this range of values the "radius of convergence" of the series.

.. math::

    \sum_{n=0}^{\infty} x^n = \frac{1}{1-x} \ \ \text{if} \ \ -1 < x < 1

and 

.. math::

    \sum_{n=0}^{\infty} ax^n = \frac{a}{1-x} \ \ \text{if} \ \ -1 < x < 1

Strang proves this equality 

.. math::

    \sum_{n=0}^{\infty} x^n = \frac{1}{1-x}
    
in an unusual way:  he shows that the derivatives all match.  Compute the derivatives of

.. math::

    f(x) = \frac{1}{1-x}
    
    f'(x) = \frac{1}{(1-x)^2}
    
    f''(x) = 2 \frac{1}{(1-x)^3}
    
    f'''(x) = 6 \frac{1}{(1-x)^4}
    
    f^n(x) = n! \frac{1}{(1-x)^n}

The term of :math:`-1`, from :math:`(1-x)` by the chain rule, keeps the derivatives positive.

At :math:`x=0` each one is :math:`n!`.  But this is also true for 

.. math::

    g(x) = 1 + x + x^2 + x^3 + \dots x^n + x^{n+1}

For the nth derivative, terms with powers smaller than :math:`x^n` vanish, those with powers greater are multiplied by zero (and vanish), all that remains is the nth derivative of :math:`x^n`, which is `n!`.


*If* the series converges, it is also possible to compute the sum.  Usually, to make things more difficult, such sums will start with a term other than :math:`x=0`.  

======================
Geometric series:  sum
======================

To compute the sum of a geometric series, use this formula:  

.. math::

    \frac{\text{first term}}{1 - \text{common ratio}}

+++++++
Example
+++++++

.. math::

    \sum_{n=1}^{\infty} \frac{1}{2^n}
    
This is the classic geometric series.  The common ratio is :math:`1/2`.  Since the ratio is between :math:`-1` and :math:`1`, the series converges.  The first term is :math:`1/2` and the value of the sum is:

.. math::

    \frac{1/2}{(1 - 1/2)} = 1

Alternatively

.. math::

    \sum_{n=0}^{\infty} \frac{1}{2^n}

This is the same as before except the first term is :math:`1` and the sum is


.. math::

    \frac{1}{(1 - 1/2)} = 2

+++++++
Example
+++++++

.. math::

    \sum_{n=5}^{\infty} \frac{4}{3^n}

    = \sum_{n=5}^{\infty} 4 \frac{1}{3^n}

This is a geometric series with common ratio :math:`1/3`.  Since the ratio is between :math:`-1` and :math:`1`, the series converges.  The first term is :math:`4/3^5` and the value of the sum is:

.. math::

    \frac{4}{3^5} / (1 - 1/3) = \frac{4/243}{2/3} = \frac{2}{81}
    
===============
Harmonic series
===============

The harmonic series is

.. math::

    \sum_{n=1}^{\infty} \frac{1}{n}
    
    = \frac{1}{1} + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} + \dots
    
(Note :math:`n` cannot be equal to :math:`0`).

The harmonic series diverges.  A classic proof is to group the terms:

.. math::

    = \frac{1}{1} + \frac{1}{2} + (\frac{1}{3} + \frac{1}{4}) + (\frac{1}{5} + \frac{1}{6} + \frac{1}{7} + \frac{1}{8}) + \dots
    
Clearly, we can continue grouping forever.  The next group has denominators from :math:`9 \dots 16`, and in general, from :math:`2^{n-1} + 1` up to :math:`2^n`.
    
The sum for each group is at least :math:`1/2`, so the series is larger term by term than:

.. math::

    = \frac{1}{1} + \frac{1}{2} + \frac{1}{2} + \frac{1}{2} + \frac{1}{2}

But this series is clearly divergent, so the harmonic series, whose sum is larger term by term, also diverges.

======================================
Series related to the geometric series
======================================

Again, the geometric series is:

.. math::

    s = 1 + x + x^2 + x^3 + \dots

+++++++++++++
Differentiate
+++++++++++++

The right-hand side is

.. math::

    1 + 2x + 3x^2 + 4x^3 + \dots

and the left-hand side is

.. math::
    
    \frac{d}{dx} \ [ \ \frac{1}{1-x} \ ] \ = \frac{1}{(1-x)^2}

Try multiplying out

.. math::

    (1-x) (1 + 2x + 3x^2 + 4x^3 + \dots )

    = 1 + 2x - x + 3x^2 - 2x^2 + 4x^3 - 3x^3 +  \dots )

    = 1 + x + x^2 + x^3 + \dots
    
    = \frac{1}{1-x}

So it checks.

And since

.. math::

    (\frac{1}{1-x})(\frac{1}{1-x}) = \frac{1}{(1-x)^2}

    (1 + x + x^2 + \dots) (1 + x + x^2 + \dots)

    = 1 + 2x + 3x^2 + 4x^3 + 5x^4 + \dots

+++++++++
Integrate
+++++++++

.. math::

    \frac{1}{1-x} = 1 + x + x^2 + x^3 + \dots
    
    \int \frac{1}{1-x} \ dx = \int 1 + x + x^2 + x^3 + \dots \ dx

    -\ln |1-x| = x + \frac{x^2}{2} + \frac{x^3}{3} + \frac{x^4}{4} + \dots
    
Even better, substitute :math:`-x` for :math:`x`

.. math::

    \frac{1}{1+x} = 1 - x + x^2 - x^3 + \dots

Integrate

.. math::

    \ln |1+x| = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \dots

    \ln 2 = 1 - \frac{1}{2} + \frac{1}{3} - \frac{1}{4} + \dots

This series converges pretty slowly.

The same series with all terms positive is the harmonic series we just looked at.

.. math::

    1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \dots

++++++++++++++++ 
Change variables
++++++++++++++++

Start with the geometric series

.. math::

    1 + x + x^2 + x^3 + \dots

Replace :math:`x` by :math:`-x^2`:

.. math::

    1 - x^2 + x^4 - x^6 + \dots = \frac{1}{1+x^2}

Now, does that right-hand side look familiar?

.. math::

    \int \frac{1}{1+x^2} \ dx = \tan^{-1} x

Integrate the left-hand side:

.. math::

    \int 1 - x^2 + x^4 - x^6 + \dots \ dx = x - \frac{x^3}{3} + \frac{x^5}{5} - \frac{x^7}{7}

Set :math:`x = 1`.  The angle with :math:`\tan^{-1} \theta = 1` is :math:`\theta = \pi/4`.  Thus:

.. math::

    \tan^{-1} 1 = \frac{\pi}{4}
    
    = 1 - \frac{1}{3} + \frac{1}{5} - \frac{1}{7}

We have found a series that equals :math:`\pi`!  How cool is that?

This particular series does not converge very fast.  But if we set :math:`x = 1/\sqrt{3}`, then the angle with that tangent is :math:`\pi/6` (recall that :math:`\sin \pi/6 = 1/2` and :math:`\cos \pi/6 = \sqrt{3}/2`), so

.. math::

    \frac{\pi}{6} = \frac{1}{\sqrt{3}} - \frac{1}{3} \ (\frac{1}{\sqrt{3}})^3 +  \frac{1}{5} \ (\frac{1}{\sqrt{3}})^5 -  \frac{1}{7} \ (\frac{1}{\sqrt{3}})^7 + \dots
    
    = \frac{1}{\sqrt{3}} (1 - \frac{1}{3} \ (\frac{1}{3}) + \frac{1}{5} \ (\frac{1}{3})^2 + \frac{1}{7} \ (\frac{1}{3})^3 \dots)
    
    = \frac{1}{\sqrt{3}} (1 - \frac{1}{9} + \frac{1}{45} - \frac{1}{189} + \frac{1}{729} - \frac{1}{2673})

:math:`\pi/6` is equal to :math:`0.5235987755982988`.

    >>> from math import sqrt
    >>> r = 1/sqrt(3)
    >>> r * (1 - 1.0/9 + 1.0/45 - 1.0/189 + 1.0/729 - 1.0/2673)
    0.5235514642438139
    >>>

This series converges fairly quickly and is actually pretty easy to compute.