.. _stirling:

########################
Stirling's Approximation
########################

Stirling's approximation is a famous and very useful approximation for factorials.  It says that:

.. math::

    n! \approx \sqrt{2 \pi n} \ \frac{n^n}{e^n}
    
    \approx \sqrt{2 \pi n} \ (\frac{n}{e})^n
    
An alternative statement is that 

.. math::

    \ln (n!) \approx n \ln n - n + O(\ln n)
    
    \ln (n!) \approx n \ln n - n + \frac{1}{2} \ln (2 \pi n)


It's interesting that :math:`\pi` should get mixed up with the factorial.

Let's compute a few values

    >>> from math import *
    >>> def s(n):
    ...     f = sqrt(2*pi*n)
    ...     return f* (n/e)**n
    ... 
    >>>
    >>> for i in range(2,20):
    ...     approx = s(i)
    ...     print str(i).rjust(2),
    ...     fact = factorial(i)
    ...     print str(fact).rjust(20),
    ...     print str(round(approx,2)).rjust(20),
    ...     print round((fact-approx)/fact,3)
    ... 
     2                    2                 1.92 0.04
     3                    6                 5.84 0.027
     4                   24                23.51 0.021
     5                  120               118.02 0.017
     6                  720               710.08 0.014
     7                 5040               4980.4 0.012
     8                40320              39902.4 0.01
     9               362880            359536.87 0.009
    10              3628800           3598695.62 0.008
    11             39916800          39615625.05 0.008
    12            479001600         475687486.47 0.007
    13           6227020800        6187239475.19 0.006
    14          87178291200        86661001740.6 0.006
    15        1307674368000     1.3004307222e+12 0.006
    16       20922789888000    2.08141144152e+13 0.005
    17      355687428096000    3.53948328666e+14 0.005
    18     6402373705728000    6.37280462619e+15 0.005
    19   121645100408832000    1.21112786592e+17 0.004
    >>> 
    
The error for :math:`n > 8` is less than 1% and continues to get better, reaching about 0.3% for :math:`n=30`.\

==========
Derivation
==========

