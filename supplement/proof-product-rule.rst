.. _proof-product-rule:

#########################
Proof of the product rule
#########################

We first construct the difference quotient and then we will find the limit:

.. math::

    \frac{d}{dx} f(x) g(x) =  \lim_{h \to 0} \frac{f(x+h)g(x+h) - f(x)g(x)}{h}

The trick (*Mooculus*) is to subtract and add :math:`f(x+h)g(x)`:

.. math::

    = \lim_{h \to 0} \frac{f(x+h)g(x+h) - f(x+h)g(x) - f(x+h)g(x) - f(x)g(x)}{h}
        
The first two terms of the numerator are

.. math::

    f(x+h)g(x+h) - f(x+h)g(x)
    
    = f(x+h) \ [ \ g(x+h) - g(x) \ ]

In the limit:

.. math::

    \lim_{h \to 0} \frac{f(x+h) \ [ \ g(x+h) - g(x) \ ]}{h}

:math:`\lim_{h \to 0} f(x+h) = f(x)` so this is just

.. math::
    
    = f(x) g'(x)

The last two terms of the difference quotient are

.. math::

    f(x+h)g(x) - f(x)g(x)

    = g(x) \ [ \ f(x+h) - f(x) \ ]

In the limit:

.. math::

    \lim_{h \to 0} \frac{g(x) \ [ f(x+h) - f(x) \ ] }{h}
    
    = g(x) f'(x)

Putting them together we obtain:

.. math::

    f(x) g'(x) + g(x) f'(x)






