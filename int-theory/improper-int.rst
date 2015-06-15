.. _improper-int:

==================
Improper integrals
==================

The log function provides a fun example of an improper integral with a very simple and finite result.  The example (and the figure) are from Hamming.

.. image:: /figs/log4.png
   :scale: 50 %

We consider the function

.. math::

    y = - \ln x = \ln \frac{1}{x}

We use the minus sign so we are working with positive :math:`y`, recognizing that the function is not defined at :math:`x=0`.  Rotate the function around the :math:`y` axis and find the volume.

To use the method of cylinders, we consider a series of concentric cylindrical surfaces of width :math:`dx`, ranging from :math:`x=0` to :math:`x=1`.  For each value of :math:`x`, the surface area is the height of the function :math:`h = - \ln x` times the circumference :math:`2 \pi x` to give a volume for each element of

.. math::

    dV = 2 \pi x \ y \ dx 
    
    = 2 \pi x \ (- \ln x) \ dx

We get the total volume by integrating

.. math::

    V = \int_0^1 2 \pi x \ (- \ln x) \ dx
    
    = - 2 \pi \int_0^1 x \ln x \ dx

What is 

.. math::

    \int x \ln x \ dx
    
The systematic approach is to use integration by parts, but let's guess.  If we had :math:`f(x) = x^2 \ln x` then part of the derivative :math:`f'(x)` would be related to what we want:

.. math::

    \frac{d}{dx} x^2 \ln x = 2 x \ln x + \frac{x^2}{x} 
    
    = 2 x \ln x + x
    
so we need another term, consisting of :math:`-x^2/2`

.. math::

    f(x) = x^2 \ln x - \frac{x^2}{2}

    f'(x) = 2 x \ln x + x - x ) 
    
    = 2 x \ln x

So

.. math::

    2 \int x \ln x \ dx =  x^2 \ln x - \frac{x^2}{2} 

The volume :math:`V` is equal to :math:`- \pi` times

.. math::

    x^2 \ln x - \frac{x^2}{2} \bigg |_0^1

At the upper limit, :math:`\ln 1 = 0` so this is :math:`-1/4`, and the question becomes, what happens to :math:`x^2 \ln x` as :math:`x` approaches :math:`0`?  We guess that :math:`x^2` must become small faster than :math:`\ln x` approaches :math:`-\infty`.  So at the lower limit, we will get zero, and the whole thing is

.. math::

    V = -2 \pi \ (-\frac{1}{4}) = \frac{\pi}{2}

Let's try by the method of disks and then come back to this limit.  We also have a figure for the second approach

.. image:: /figs/log5.png
   :scale: 50 %

As :math:`y` ranges from :math:`0` to :math:`\infty`, each disk has a width :math:`dy` and an area equal to :math:`\pi x^2` so the volume element is

.. math::

    dV = \pi x^2 \ dy

We change variables and write

.. math::

    y = - \ln x

    dy = - \frac{1}{x} \ dx

so

.. math::

    dV = - \pi x^2 \ \frac{1}{x} \ dx 
    
    = - \pi x \ dx

The limits also change.  Before we had :math:`y = 0 \rightarrow \infty` and now we have :math:`x = 1 \rightarrow 0` so

.. math::

    V = \int_1^0 - \pi x \ dx

    = \pi \int_0^1 x dx

    = \frac{\pi}{2} x^2 \ \bigg |_0^1 =  \frac{\pi}{2}

So it looks like we were right about that limit.  But what is the formal method for evaluating

.. math::

    \lim_{x \rightarrow 0} x^2 \ln x

We convert this to a fraction

.. math::

    \lim_{x \rightarrow 0} \frac{\ln x}{1/x^{2}}

Since both numerator and the denominator go to :math:`\infty` as :math:`x \rightarrow 0`, this is an indeterminate form, and we can use :ref:`L'Hopital's rule <LHopital>`.  We need derivatives of the numerator and the denominator.  The numerator gives :math:`1/x` and the denominator gives :math:`-2/x^{3}` so we have

.. math::

    \frac{1}{x} \ \frac{1}{-2/x^{-3}} = \frac{x^3}{x}(- \frac{1}{2}) = - \frac{x^2}{2}

which in the limit as :math:`x \rightarrow 0`, also goes to :math:`0`.

Generally speaking, with an improper integral one of three conditions holds:  the upper bound is :math:`+ \infty`, the lower bound is :math:`- \infty`, or at either the upper or lower bound, the value of the function is undefined (:math:`\rightarrow \pm \infty`.  (If the value is undefined in the middle of a range, break the integral into pieces).

We integrate the function anyway, and if, when we evaluate it at that bound, we get :math:`0`, then we can use the result.  This example was a little more complicated, so let's look at a simpler one:

.. math::

    \int_0^{\infty} e^{-x} \ dx

    = - e^{-x} \ \bigg |_0^{\infty}

    = (-0) - (-1) = 1

So we could look at the negative exponential as a probability density function.  Since the total area over the range :math:`[- \infty, \infty]` is twice this (i.e. :math:`2`), we should normalize the total probability to :math:`1` by dividing by :math:`2`.