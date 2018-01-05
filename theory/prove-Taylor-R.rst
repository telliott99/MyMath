.. _prove-Taylor-R:

###############################
Taylor Series Remainder:  Proof
###############################

From :ref:`here <taylor>`, the terms of the Taylor series is:

.. math::

    \sum_0^{\infty} f^n(a) \frac{(x-a)^n}{n!}

where :math:`a` is a value for which we know how to calculate :math:`f(a)`, and :math:`x` may be some value nearby where we wish to estimate :math:`f(x)`, or an interval over which we want to integrate, or something.

In estimation, we will truncate the series, say at the Taylor polynomial of degree :math:`n`.  The series is

.. math::

    f(a) + f'(a) (x-a) + f''(a) \frac{(x-a)^2}{2} + \dots + f^n(a) \frac{(x-a)^n}{n!} + f^n(a) \frac{(x-a)^{n+1}}{(n+1)!} + \dots
    
We estimate :math:`f(x)` by setting

.. math::

    T_n = (a) + f'(a) (x-a) + f''(a) \frac{(x-a)^2}{2} + \dots + f^n(a) \frac{(x-a)^n}{n!}

and then 

.. math::

    f(x) = T_n + f^n(a) \frac{(x-a)^{n+1}}{(n+1)!} + \dots
    
Now the difference between :math:`f(x)` and :math:`T_n` is the error in the estimation.

.. math::

    f(x) = Tn + Rn

The Remainder theorem (:ref:`here <taylor-remainder>`) says that 

.. math::

    R_n = f^n(c) \frac{(x-a)^{n+1}}{(n+1)!}
    
No dots, just one term!  Here :math:`c` is some value between :math:`x` and :math:`a`.

And, as we said before, this certainly makes sense.  If we truncate at :math:`n=0` we have

    f(x) = f(a) + R_n
    
    = f(a) + f'(c) (x-a)
    
    \frac{f(x) - f(a)}{(x-a)} = f'(c)

for some :math:`c` between :math:`x` and :math:`a`.  This is just the mean value theorem.

=====
Proof
=====

So although the theorem is certainly true for :math:`n=0` we'd like to prove that it is true for *any* n.  To do this, we prove it for some reasonable value, and show that the proof is generalizable to any :math:`n`.

(not yet done:  Varberg p. 468)
    
