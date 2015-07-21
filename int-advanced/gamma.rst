.. _gamma:

##############
Gamma function
##############

We start with :ref:`Euler's factorial <euler-factorial>`, that for integral :math:`n \ge 0`

.. math::

    n! = \int_0^{\infty} t^n e^{-t} \ dt

We now generalize to any :math:`x > 0` and say that

.. math::

    \Gamma(x) = \int_0^{\infty} t^x e^{-t} \ \frac{dt}{t}
    
    = \int_0^{\infty} t^{x-1} e^{-t} \ dt

For integer :math:`n`

.. math::

    \Gamma(n) = (n-1)!
    
The reason for the translation of :math:`n` (and :math:`x`) is to obtain a good "domain" for :math:`x` (i.e. :math:`[0,+\infty]`).  See 

http://www.sosmath.com/calculus/improper/gamma/gamma.html

One of the most important properties of the gamma function is that

.. math::

    \Gamma (x+1) = x \Gamma(x)

To prove this, we use integration by parts.

.. math::

    \Gamma(x) = \int_0^{\infty} t^{x-1} e^{-t} \ dt
    
Let

.. math::

    u = t^{x-1}
    
    du = (x-1)t^{x-2} \ dt
    
    dv = e^{-t} dt
    
    v = -e^{-t}

So the integral becomes:

.. math::

    \Gamma(x) = -t^{x-1} \ e^{-t} + \int_0^{\infty} (x-1)t^{x-2} \ e^{-t} \ dt
    
The first term is zero by the same argument we used :ref:`before<euler-factorial>` and the second term is 

.. math::

    \Gamma(x) = (x-1) \int_0^{\infty} t^{x-2} \ e^{-t} \ dt
    
    = (x-1) \Gamma(x-1)
    
A consequence of this property is that knowing :math:`\Gamma(x)` on the interval :math:`[0,1]` we can compute it for any :math:`x`.

.. math::

    \Gamma (x + n) = (x + n - 1) (x + n - 2) \dots (x + 1) \ x \ \Gamma(x)

==========
Properties
==========

The first important property is:

.. math::

    \Gamma(x) = (x-1) \ \Gamma(x-1)
    
    \Gamma(0) = 1

(Alternatively):

.. math::

    \Gamma(x+1) = x \ \Gamma(x)

A second property that I got from here:

http://www.math.uconn.edu/~kconrad/blurbs/analysis/gaussianintegral.pdf

.. math::
    
    \frac{\Gamma(x) \Gamma(y)}{\Gamma (x+y)} = \int_0^1 t^{x-1}(1-t)^{y-1} \ dt

(Need to justify this).

We used this :ref:`here <gauss-again2>` in deriving the total area under the Gaussian (normal) distribution.

++++++++++++
Applications
++++++++++++

The Gamma function allows solutions of integrals that would stump us in the past.  For a great example see :ref:`the Gaussian integral <gauss-again2>`.  Here is another:

.. math::

    \int_0^{\infty} e^{-x^4} \ dx

Try U-substitution.  Let:

.. math::

    u = x^4
    
    du = 4x^3 \ dx
    
    dx = \frac{1}{4} \ x^{-3} \ du
    
    u^{3/4} = (x^4)^{3/4} = x^3
    
So

.. math::

    \int_0^{\infty} e^{-x^4} \ dx 
    
    = \frac{1}{4} \int_0^{\infty} x^{-3} e^{-u} \ du
    
    = \frac{1}{4} \int_0^{\infty} u^{-3/4} \ e^{-u} \ du
    
If we compare with the definition of the Gamma function:

.. math::

    \Gamma(x) = \int_0^{\infty} t^{x-1} e^{-t} \ dt

Switching notation:

.. math::

    \Gamma(n) = \int_0^{\infty} x^{n-1} e^{-x} \ dx

So our integral is:

.. math::

    \frac{1}{4} \int_0^{\infty} u^{-3/4} \ e^{-u} \ du = \frac{1}{4} \ \Gamma(\frac{1}{4})

Using the following property:

.. math::

    \Gamma(x+1) = x \ \Gamma(x)

we obtain:

.. math::
    
    \int_0^{\infty} e^{-x^4} \ dx = \Gamma(\frac{5}{4})


    