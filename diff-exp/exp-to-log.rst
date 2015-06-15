.. _exp-to-log:

#####################################
The exponential is its own derivative
#####################################

================================
Derivation of the series for e^x
================================

A series for :math:`e^x` is:

.. math::

    e^x = \frac{x^0}{0!} + \frac{x^1}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots

    = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots    

This can be derived from the binomial expansion (see :ref:`here <exp-binomial>`).


Needs work!!!

It can also be obtained from a Maclaurin series which goes as follows:

.. math::

    \sum_{n=0}^{\infty} \frac{f^n(x)(x)^n}{n!}
    
    = e^x + \frac{e^x x^1}{1!} + \frac{e^x x^1}{1!}


    e^x = e(1)\frac{x^{1-1}}{1!} + (2)\frac{x^{2-1}}{2!} + (3)\frac{x^{3-1}}{3!} + \cdots


A most important fact about the exponential function :math:`f(x) = e^x` is that this function is its own derivative.  To see that, take :math:`\frac{d}{dx}` of the last series.

.. math::

    \frac{d}{dx} \ e^x = 0 + (1)\frac{x^{1-1}}{1!} + (2)\frac{x^{2-1}}{2!} + (3)\frac{x^{3-1}}{3!} + \cdots

    \frac{d}{dx} \ e^x = 0 + \frac{x^{0}}{0!} + \frac{x^{1}}{1!} + \frac{x^{2}}{2!} + \cdots

    = e^x

Each exponent :math:`n` that comes down through the power rule, finds an :math:`n` in :math:`n!=n \times (n-1) \times (n-2) \dots` to cancel, leaving :math:`n-1` in the exponent as well as :math:`(n-1)!`.

We can find the derivative of a generic exponential using the standard method with the difference quotient.  Let :math:`b` be the base, then :math:`f(x) = b^x` and

.. math::

    \lim_{h \to 0}    \ \frac{b^{x+h} - b^x}{h}

But

.. math::

    b^{x+h} = b^x b^h

so this is just

.. math::

    \lim_{h \to 0}    \ \frac{b^xb^h - b^h}{h}

    = \lim_{h \to 0}    \ \frac{b^x(b^h - 1)}{h}

    = b^x  \lim_{h \to 0}\ \frac{(b^h - 1)}{h} = cb^x

We didn't ever say exactly what the value of :math:`c` is, just that it is just a number which depends on :math:`b`, but *not* on :math:`x`, so we know it's a constant.  It turns out that 

.. math::

    c = \log_b e

So if :math:`b = e`, then :math:`c=1`.  You can see that by looking at

.. math::

    \lim_{h \to 0}\ \frac{(e^h - 1)}{h}

For small :math:`h` we can approximate :math:`e^h = 1 + h` (see the series above), then

.. math::

    \lim_{h \to 0}\ \frac{(1 + h - 1)}{h} = \frac{h}{h} = 1

===========
One problem
===========

I don't have a lot of problems in this write-up but I will put two here about integration of the exponential.  Since

.. math::

    \frac{d}{dx} e^x = e^x

and by the chain rule

.. math::

    \frac{d}{dx} e^{f(x)} = e^{f(x)} f'(x)

And generally, for :math:`u = u(x)` have that 

.. math::

    \int e^u \ du = e^u + C

So what is 

.. math::

    \int x e^x \ dx

.. math::

The systematic approach uses integration by parts, but we can get there by just playing with the derivative

.. math::

    \frac{d}{dx} \ x e^x = x e^x + e^x

so 

.. math::

    \int \frac{d}{dx} \ x e^x \ dx = \int x e^x \ dx + \int e^x \ dx

    x e^x = \int x e^x \ dx + e^x

    \int x e^x \ dx = x e^x - e^x

The second one requires a special trick.  

.. math::

    \int_0^{\infty} \frac{1}{1 + e^x} \ dx

Multiply by :math:`e^{-x}` on top and bottom

.. math::

    \int_0^{\infty} \frac{e^{-x}}{1 + e^{-x}} \ dx

This is just :math:`\int 1/u \ du`.  Remember the minus sign

.. math::

    = - \ln (1 + e^{-x}) \ \bigg |_0^{\infty}

At the upper limit we obtain :math:`\ln 1 = 0` and at the lower limit we have 

.. math::

    - - \ln 2 = \ln 2

so

.. math::

    \int_0^{\infty} \frac{1}{1 + e^x} \ dx = \ln 2

=============================
From exponential to logarithm
=============================

It is possible to obtain the definition of the derivative of the logarithm from:

.. math::

    \int \frac{1}{t} \ dt = \ln(t)

    \frac{d}{dt} \int \frac{1}{t} \ dt  
    
    = \frac{1}{t}  = \frac{d}{dt} \ln(t)

This is great because we never did generate :math:`x^{-1}` by differentiating powers of :math:`x1`.  Now we know how to go back the other way.  

The proof is so simple that if you blink, you'll miss it.  Again, we found that the exponential function is its own derivative.  That is

.. math::

    y = e^x

    \frac{d}{dx} e^x = \frac{dy}{dx} = e^x

    \frac{dy}{dx} = y

Invert

.. math::

    \frac{dx}{dy} = \frac{1}{y}

    dx = \frac{1}{y} \ dy

Integrate

.. math::

    \int dx = x = \int \frac{1}{y} \ dy

And what is :math:`x`?  It is :math:`\ln(y)`!

.. math::

    \ln(y) = \int \frac{1}{y} \ dy

And since :math:`y` is just a letter, we can write the same for :math:`x`, or :math:`t`

.. math::

    \ln(t) = \int \frac{1}{t} \ dt

One of the prettiest things I've ever seen.

The math purists don't like it, but in general it is OK to do algebra with differentials.  One important restriction is that :math:`dy/dx` (and :math:`dx/dy`) should not be equal to zero.  And a second one is that we just remember we are never passing to the limit, just getting really, really, really close.  (As close as you like).

Now that we have this definition, we have another way of estimating the value of :math:`e`.  We add up the areas for little slices under the function :math:`y=1/x` until we reach :math:`1`.  That value of :math:`x=e`.

.. image:: /figs/log3.png
   :scale: 50 %

(from Hamming's *Calculus*).

For example, we might try intervals of :math:`0.1` and do

.. math::

    0.1 \cdot \frac{1}{1} + 0.1 \cdot \frac{1}{1.1} + 0.1 \cdot \frac{1}{1.2} + \dots + 0.1 \cdot \frac{1}{2.7}

I tried this in Python, but it didn't work so well.  (Need to figure this out).