.. _binomial-theorem:

################
Binomial Theorem
################

==========================
Positive integer exponents
==========================

In algebra we learn that

.. math::

    (a + b) \times c = ac + bc

This is called the distributive law of multiplication.  And

.. math::

    (a + b) \times (c + d) = ac + ad + bc + bd
    
If :math:`a = c` and :math:`b = d`, then

.. math::

    (a + b) \times (a + b) = aa + ab + ba + bb
    
    = a^2 + 2ab + b^2

which is normally written as:

.. math::

    (a + b)^2 = a^2 + 2ab + b^2

and

.. math::

    (a + b)^3 = (a + b) (a^2 + 2ab + b^2)
    
    = a^3 + 2a^2b + ab^2 + ba^2 + 2ab^2 + b^3
    
    = a^3 + 3a^2b + 3ab^2 + b^3
    
Continuing

.. math::

    (a + b)^4 = (a + b) (a^3 + 3a^2b + 3ab^2 + b^3)
    
    = a^4 + 3a^3b + ba^3 + \dots
    
    = a^4 + 4a^3b

It is easy to see that the general rule for the first two terms is

.. math::

    (a + b)^n = a^n + na^{n-1}b

==========================
Negative integer exponents
==========================

.. math::

    (a + b)^{-1} = \frac{1}{a + b}

Let's work for a minute with :math:`(1 + x)` and :math:`(1 - x)`:

.. math::

    \frac{1}{1 + x} = \ ?
    
    \frac{1}{1 - x} = \ ?

It takes insight to see that:

.. math::

    \frac{1}{1 - x} = 1 + x + x^2 + x^3 + \dots
    
This can be demonstrated by grouping the terms from multiplying the right-hand side by the denominator :math:`(1-x)` into two sets of terms

.. math::

    1 = (1-x) (1 + x + x^2 + x^3 + \dots)
    
    = 1 + x + x^2 + x^3 + \dots +
    
        - x - x^2 - x^3 + \dots
        
    = 1

Even though the series for :math:`1/(1-x)` is an *infinite* series, in the multiplication we obtain two series where the equivalent terms have opposite sign and so they all cancel.

In a similar way

.. math::

    \frac{1}{1 + x} = 1 - x + x^2 - x^3 + \dots


.. math::

    1 = (1+x) (1 - x + x^2 - x^3 + \dots)
    
    = 1 - x + x^2 - x^3 + \dots +
    
        + x - x^2 + x^3 + \dots
        
    = 1

Again we have a cancellation.

Now, if the power rule is valid for negative integer exponents then

.. math::

    \frac{d}{dx} \ \frac{1}{(1 + x)}
    
    = \frac{d}{dx} (1 + x)^{-1}
    
    = - (1 + x)^{-2}
    
    = - \frac{1}{(1 + x)^2}
    
and this must be equal to the derivative of the equivalent series

.. math::

    \frac{d}{dx} \ (1 - x + x^2 - x^3 + \dots )
    
    = - 1 + 2x - 3x^2 + \dots

So is it true that:

.. math::

    - \frac{1}{(1 + x)^2} = - 1 + 2x - 3x^2 + \dots

Canceling the minus signs:

.. math::

    \frac{1}{(1 + x)^2} = 1 - 2x + 3x^2 + \dots
    
Check by multiplying out:

.. math::

    \frac{1}{1 + x} \stackrel{?}{=} (1 + x) (1 - 2x + 3x^2 + \dots)
    
    = 1 - 2x + 3x^2 + \dots
    
        + x - 2x^2 + \dots
    
    = 1 - x + x^2 + \dots
    
    = \frac{1}{1 + x}

Seems to work but actually proving the generalized binomial is a challenge.  (Newton used it but I'm not sure he proved it).  In any event, we proved that the power rule works for fractional exponents by :ref:`implicit differentiation <frac_powers>`, but, we did not actually prove that implicit differentiation is itself valid.
