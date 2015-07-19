.. _logarithmic_diff:

###########################
Logarithmic Differentiation
###########################

Here is the first problem Paul uses for this topic.  

http://tutorial.math.lamar.edu/Classes/CalcI/LogDiff.aspx

Differentiate

.. math::

    y = \frac{x^5}{(1-10x)\sqrt{x^2+2}}

We could use the product, quotient and chain rules for this (and we can be sure it will be messy in the end).  An alternative is to use the properties of the logarithm to break the right-hand side into a polynomial.  Take the logarithm of both sides

.. math::

    \ln y = \ln (\frac{x^5}{(1-10x)\sqrt{x^2+2}} )

    \ln y = \ln(x^5) - \ln(1-10x) - \ln(\sqrt{x^2+2})

Now, when we differentiate, it is really implicit differentiation.

The way I do this is to imagine that both :math:`y` and :math:`x` are functions of :math:`t` (e.g. :math:`x=t`).  Then the one term from the left and three from the right are

.. math::

    \frac{d}{dt} \ln y = \frac{1}{y} \frac{dy}{dt}

.. math::

    \frac{d}{dt} \ln (x^5) = \frac{1}{x^5} 5x^4 \frac{dx}{dt}  = \frac{5}{x} \frac{dx}{dt}

.. math::

    \frac{d}{dt} \ln (1-10x) = \frac{1}{(1-10x)} (-10) \frac{dx}{dt} = - \frac{10}{(1-10x)} \frac{dx}{dt}

.. math::

    \frac{d}{dt} \ln (\sqrt{x^2+2} = \frac{1}{\sqrt{x^2+2}} \frac{1}{2\sqrt{x^2+2}} 2x \frac{dx}{dt} 

    = \frac{x}{x^2 + 2}  \frac{dx}{dt}

Every term has :math:`dt` in the denominator, so that just cancels.  Bring the :math:`dx` from every term on the right to the left-hand side.  On the left we get

.. math::

    \frac{1}{y} \frac{dy}{dx} = \frac{y'}{y}

When working problems of this type, in the future we will start here:  with the above on the left-hand side, and then differentiate the log of the right-hand side. 

In this case, for the rest we have

.. math::

    \frac{y'}{y} =   \frac{5}{x} + \frac{10}{(1-10x)} - \frac{x}{x^2 + 2}

To finish the problem, we need to multiply through by :math:`y`

.. math::

    y' = (\frac{x^5}{(1-10x)\sqrt{x^2+2}}) ( \frac{5}{x} + \frac{10}{(1-10x)} - \frac{x}{x^2 + 2})

which I won't try to simplify.
    
==============
Useful results
==============

Besides these (painful and rather silly) algebraic manipulations, the main thing about logarithmic differentiation is that it allows us to solve a problem we couldn't do until now.  Differentiate

.. math::

    y = x^x = \ ?

Take the log and differentiate

.. math::

    \frac{dy}{y} = \frac{d}{dx} \ x \ln x

    \frac{y'}{y} = x (\frac{1}{x}) + \ln x (1) = 1 + \ln x
    
So 

.. math::

    y' = x^x (1 + \ln x)

Another useful result is to prove the power rule.  We want

.. math::

    \frac{d}{dx} x^n

where :math:`n` is not just a positive or negative integer (:math:`\ne -1`), but can be any real number, like :math:`\pi` or :math:`e` or :math:`\sqrt{2}`.

As we did above, for logarithmic differentiation on the left-hand side we have :math:`y'/y`:

.. math::

    \frac{dy}{y} = \frac{d}{dx} n \ln x
    
    \frac{dy}{y} = n \ \frac{1}{x} \ dx
    
    \frac{y'}{y} = n \ \frac{1}{x}

So 

.. math::

    y' = n \ \frac{1}{x} x^n
    
    = n x^{n-1}

which is the power rule.

+++++++
Example
+++++++

Another unwieldy problem that can be solved by logarithmic differentiation:

.. math::

    \frac{d}{dx} \ [ \ \frac{x^9 e^{4x}}{\sqrt{x^2 + 4}} \ ]

We could write this as

.. math::

    \frac{f(x) g(x)}{h(x)}

And solve it using the product rule and the quotient rule.  Or we can take the logarithm

.. math::

    \ln f(x) = \ln x^9 + \ln e^{4x} - \ln \sqrt{x^2 + 4}

    = 9 \ln x + 4x - \frac{1}{2} \ln (x^2 + 4)

and then take the derivative

.. math::

    \frac{9}{x} + 4 - \frac{x}{(x^2 + 4)}

and then apply the rule:

.. math::

    \frac{d}{dx} \ln f(x) = \frac{f'(x)}{f(x)}

So we multiply by :math:`f(x)` to obtain the result:

.. math::

    f'(x) = ( \frac{9}{x} + 4 - \frac{x}{(x^2 + 4)}) \  \frac{x^9 e^{4x}}{\sqrt{x^2 + 4}}

which would obviously be a real mess by the standard approach.

:ref:`Here <max_likelihood>` is a nice application.