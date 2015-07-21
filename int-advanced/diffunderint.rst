.. _diffunderint:

###################################
Differentiation: under the integral
###################################

We start with a reference to Euler's factorial formula (see :ref:`here <euler-factorial>`):  for integral :math:`n \ge 0`

.. math::

    n! = \int_0^{\infty} t^n e^{-t} \ dt

We're going to derive this in a different way, using the following rule:

.. math::

    \frac{d}{dt} \ \int_a^b f(x,t) \ dt = \int_a^b \frac{\partial}{\partial t} f(x,t) \ dx

This is called **differentiating under the integral sign**.
    
What it means is that if we have a function of two variables :math:`x` *and* :math:`t`, then the above is true.

The simple version of the rule (as we have it here) was discovered by Leibnitz and is called (of course) the Leibnitz Rule.

Here is a proof:

http://math.hawaii.edu/~rharron/teaching/MAT203/LeibnizRule.pdf

+++++++
Example
+++++++

Let's start with Euler's formula for the base case (:math:`n = 0`) substituting :math:`x` for :math:`t` as the variable:

.. math::

    \int_0^{\infty} e^{-x} \ dx = 1

We do this because we want to introduce :math:`t` as a *parameter*.  Let

.. math::

    x = tu, \ \ \ t > 0
    
    dx = t \ du
    
    \int_0^{\infty} t e^{-tu} \ du = 1
    
So

.. math::

    \int_0^{\infty} e^{-tu} \ du = \frac{1}{t}
    
(since :math:`t` does not depend on :math:`u`).  And now we switch back to :math:`x` because it's our favorite:

.. math::

    \int_0^{\infty} e^{-tx} \ dx = \frac{1}{t}

And now apply the rule:

.. math::

    \int_0^{\infty} \frac{\partial}{\partial t} e^{-tx} \ dx = \frac{d}{dt} \ \frac{1}{t}

    \int_0^{\infty} -x e^{-tx} \ dx = -t^{-2}

    \int_0^{\infty} x e^{-tx} \ dx = t^{-2}

This can be continued indefinitely:

.. math::

    \int_0^{\infty} x^2 e^{-tx} \ dx = 2t^{-3}

    \int_0^{\infty} x^3 e^{-tx} \ dx = 3! \ t^{-4}

    \int_0^{\infty} x^n e^{-tx} \ dx = \frac{n!}{t^{n+1}}

Finally just let :math:`t = 1`:

.. math::

    \int_0^{\infty} x^n e^{-x} \ dx = n!

References:

http://ocw.mit.edu/courses/mathematics/18-304-undergraduate-seminar-in-discrete-mathematics-spring-2006/projects/integratnfeynman.pdf

   