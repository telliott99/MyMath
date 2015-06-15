.. _ibp_more:

###################
IBP:  more problems
###################

I came across a video on MIT's ocw site giving four problems that are a little harder than what we've done above.  I thought I would work through them here.

+++++++++
Problem 1
+++++++++

.. math::

    \int x e^{-x} \ dx

We want to have the "u part" include stuff that will be easier after differentiation.  So

.. math::

    u = x, \ \ du = dx

    dv = e^{-x} \ dx, \ \ v = -e^{-x}

    \int u \ dv = uv - \int v \ du

    uv = -xe^{-x}

    \int v \ du = \int -e^{-x} \ dx = e^{-x}

    \int x e^{-x} \ dx  =  -xe^{-x} - e^{-x} = -e^{-x}(1 + x)

Now

.. math::

    \frac{d}{dx} -e^{-x}(1 + x) = -[ \ e^{-x} + (1 + x)(-e^{-x}) ] = xe^{-x}

So it checks.

+++++++++
Problem 2
+++++++++

.. math::

    \int \frac{x^3}{(1+x^2)^2} \ dx

There's a trick here, which is to see that the :math:`x^3` should be split up, since one :math:`x` will serve as part of :math:`dv` to be integrated.

.. math::

    u = x^2, \ \ du = 2 x \ dx

    dv = \frac{x}{(1+x^2)^2} \ dx, \ \ v = -\frac{1}{2}(\frac{1}{(1+x^2)}

so

.. math::

    \int u \ dv = uv - \int v \ du

    uv = -\frac{x^2}{2}(\frac{1}{(1+x^2)}

    \int v \ du = -\frac{1}{2}(\frac{1}{(1+x^2)} \ 2x \ dx 
    
    = - \int \frac{x}{(1+x^2)} \ dx 
    
    = - \frac{1}{2} \ [ \ ln(1+x^2) \ ]

    \int \frac{x^3}{(1+x^2)^2} \ dx = -\frac{x^2}{2}(\frac{1}{(1+x^2)}) + \frac{1}{2} \ [ \ ln(1+x^2) 
    
    =  \frac{1}{2}[ln(1+x^2) - \frac{x^2}{(1+x^2)} ]

Now

.. math::

    \frac{d}{dx} [ \ \frac{1}{2}[ln(1+x^2) - \frac{x^2}{(1+x^2)}] = \ ??

Let's do one piece at a time

.. math::

    \frac{d}{dx} ln(1+x^2) = \frac{2x}{(1+x^2)}

    \frac{d}{dx} \frac{x^2}{(1+x^2)} = \frac{(1+x^2)2x - x^2(2x)}{(1+x^2)^2} =\frac{2x}{(1+x^2)} -  \frac{2x^3}{(1+x^2)^2}

Notice the minus sign between the two terms we are differentiating, that means we can cancel the terms :math:`2x/(1+x)^2` and switch the sign of the :math:`x^3` term, and then have

.. math::

    \frac{1}{2} \frac{2x^3}{(1+x^2)^2} = \frac{x^3}{(1+x^2)^2}

So it checks.

+++++++++
Problem 3
+++++++++

.. math::

    \int \frac{\ln x}{x^2} \ dx

We can integrate :math:`\ln x` (see above).  But usually, simplification comes by going in the opposite direction, so put it in :math:`u`

.. math::

    u = \ln x, \ \ du = \frac{1}{x} \ dx

    dv = \frac{1}{x^2} \ dx, \ \ v = -x^{-1} = -\frac{1}{x}

    \int u \ dv = uv - \int v \ du

    uv = -\frac{1}{x} \ln x

    \int v \ du = \int -\frac{1}{x^2} \ dx = \frac{1}{x}

    \int \frac{\ln x}{x^2} \ dx = -\frac{1}{x} \ln x - \frac{1}{x} = -\frac{1}{x}(1 + \ln x)

Now

.. math::

    \frac{d}{dx} [ \ -\frac{1}{x}(1 + \ln x) \ ] = -\frac{1}{x^2} + \frac{(1 + \ln x)}{x^2} = \frac{\ln x}{x^2}

So it checks.

+++++++++
Problem 4
+++++++++

.. math::

    \int \arctan \ x \ dx

It doesn't look like we have two terms here.  But we do..

.. math::

    u = \arctan \ x, \ \ du =  \frac{1}{(1+x^2)} \ dx

    dv = 1 \ dx, \ \ v = x

    \int u \ dv = uv - \int v \ du

    uv = x \arctan \ x

    \int v \ du = \int  \frac{x}{(1+x^2)} \ dx = \frac{1}{2} \ln (1+x^2)

    \int \arctan \ x \ dx = x \arctan \ x - \frac{1}{2} \ln (1+x^2)

Now

.. math::

    \frac{d}{dx} [ \ x \arctan \ x - \frac{1}{2} \ln (1+x^2) = ??

The first term is

.. math::

    \frac{x}{(1+x^2)} + \arctan \ x

and the second is

.. math::

    - \frac{x}{(1+x^2)}

So it checks.

++++++++++++
Last problem
++++++++++++

.. math::

    \int p^3 e^{-p^2} \ dp

    u = p^2, \ \ du =  2p \ dp

    dv = pe^{-p^2}, \ \ v = -\frac{1}{2} \ e^{-p^2}

    \int u \ dv = uv - \int v \ du

    uv = -\frac{1}{2} \ p^2 e^{-p^2}

    \int v \ du = \int -\frac{1}{2} \ e^{-p^2} \ 2p \ dp = -\int p \ e^{-p^2} \ dp = \frac{1}{2} \ e^{-p^2}

    \int p^3 e^{-p^2} \ dp = -\frac{1}{2} \ p^2 e^{-p^2} - \frac{1}{2} \ e^{-p^2} =  -\frac{1}{2} \ e^{-p^2}(1 + p^2)

I also did this a different way, with a double substitution, same answer.

.. math::

    \int p^3 e^{-p^2} \ dp

    x = e^{-p^2}, \ \ dx =  -2p e^{-p^2} \ dp, \ \ -p^2 = \ln x
    
!!

.. math::

    \int p^3 e^{-p^2} \ dp = \frac{1}{2} \int \ln x \ dx

This one is integration by parts too, but perhaps we can just guess.

.. math::

    \frac{d}{dx} (x\ln x - x) = x \frac{1}{x} + \ln x - 1 = \ln x

Pick up the factor of :math:`1/2`

.. math::

    \frac{1}{2} \ ( x \ln x - x) = \frac{1}{2} \ [\ (-e^{-p^2}p^2) - e^{-p^2} \ ] \ = -\frac{1}{2} \ e^{-p^2}(1  + p^2)

which is just what we had before.
