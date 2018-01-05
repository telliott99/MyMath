.. _diffunderint:

###################################
Differentiation: under the integral
###################################

We start with a reference to Euler's factorial formula (see :ref:`here <euler-factorial>`):  for integral :math:`n \ge 0`.

.. math::

    n! = \int_0^{\infty} t^n e^{-t} \ dt
    
We're going to derive this in a different way, using what is called the Leibnitz rule.  The following is true for any function of two variables :math:`x` and :math:`y`, given that :math:`\partial y/\partial x` is continuous:

.. math::

    \frac{d}{dy} \ \int_a^b f(x,y) \ dx = \int_a^b \frac{\partial}{\partial y} f(x,y) \ dx

This is called **differentiating under the integral sign**.
    
Here is a proof:

http://math.hawaii.edu/~rharron/teaching/MAT203/LeibnizRule.pdf

+++++++
Example
+++++++

Let's start with Euler's formula for the base case (:math:`n = 0`) changing notation to substitute :math:`x` for :math:`t` as the variable:

.. math::

    \int_0^{\infty} e^{-x} \ dx = 1

This is a standard example of an improper integral.  We evaluate the integral at some finite upper limit :math:`b` and then ask what happens in the limit as :math:`b \rightarrow \infty`.

I changed notation because I want to introduce the symbol :math:`t` as a *parameter*.  Let

.. math::

    x = tu, \ \ \ t > 0
    
    dx = t \ du
    
    \int_0^{\infty} t e^{-tu} \ du = 1
    
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

+++++++
Example
+++++++

Shankar uses as an example a series of functions related to the Gaussian (see :ref:`here <gauss-again2>`)

.. math::

    I_0(a) = \int_0^{\infty} e^{-ax^2} \ dx
    
    I_1(a) = \int_0^{\infty} e^{-ax^2} \ x \ dx

and so on.  The notation :math:`I(a)` indicates that we will (eventually) view these guys as a function of the parameter :math:`a`.

The first one is (one-half) the Gaussian integral and we will just assume the answer here:

.. math::

    I_0(a) = \int_0^{\infty} e^{-ax^2} \ dx = \frac{1}{2} \ \sqrt{\frac{\pi}{a}}

The second one is straightforward to evaluate since we have the derivative of what's in the exponent:

.. math::

    I_1(a) = \int_0^{\infty} e^{-ax^2} \ x \ dx = -\frac{1}{2a} \ [ e^{-ax^2} \  ] \ \bigg |_0^{\infty}

    = -\frac{1}{2a} \ (-1) = \frac{1}{2a}

What we're going to do is start from :math:`I_0(a)` and differentiate with respect to :math:`a`.  (Recall the rule from above).  We will have:

.. math::

    \int_0^{\infty} \frac{\partial}{\partial a} \ e^{-ax^2} \ dx = \frac{d}{da} \ \frac{1}{2} \ \sqrt{\frac{\pi}{a}}

    \int_0^{\infty} \ e^{-ax^2} \ (-x^2) \ dx = -\frac{1}{4} \ \sqrt{\pi} a^{-3/2}

    I_2(a) = \int_0^{\infty} \ e^{-ax^2} \ x^2 \ dx = \frac{1}{4} \ \sqrt{\pi} a^{-3/2}
    
    I_4(a) = \int_0^{\infty} \ e^{-ax^2} \ x^4 \ dx = \frac{3}{8} \ \sqrt{\pi} a^{-5/2}

and so on.  For the odd functions do this:

.. math::

    I_1(a) = \int_0^{\infty} e^{-ax^2} \ x \ dx = \frac{1}{2a}

    \int_0^{\infty} \frac{\partial}{\partial a} \ e^{-ax^2} \ x \ dx = \frac{d}{da} \ \frac{1}{2a}

    - \int_0^{\infty} \ e^{-ax^2} \ x^3 \ dx = - \frac{1}{2a^2}

    I_3(a) = \int_0^{\infty} \ e^{-ax^2} \ x^3 \ dx = \frac{1}{2a^2}
    
+++++++
Example
+++++++

Another one is the integral which yields the inverse tangent:

.. math::

    \int_0^{\infty} \frac{1}{1 + x^2} \ dx 
    
    = \tan^{-1} x \bigg |_0^{\infty} = \frac{\pi}{2}

It's easy to solve this with a trig substitution (see :ref:`here <inverse_trig>`):

.. math::

    x = \tan \theta
    
    dx = \sec^2 \theta \ d \theta
    
    \frac{1}{1 + x^2} = \cos^2 \theta
    
The integral is just :math:`\int d \theta = \theta = \tan^{-1} x`.

Suppose we have

.. math::

    \int_0^{\infty} \frac{1}{a^2 + x^2} \ dx

One way to solve this is to scale :math:`x`:

.. math::

    x = au
    
    dx = a \ du
    
    \int_0^{\infty} \frac{1}{a^2 + x^2} \ dx = a \int_0^{\infty} \frac{1}{a^2 + a^2u^2} \ du

    = a \int_0^{\infty} \frac{1}{a^2} \ \frac{1}{1 + u^2} \ du

    = \frac{1}{a} \int_0^{\infty} \ \frac{1}{1 + u^2} \ du
    
    = \frac{1}{a} \tan^{-1} u \ \bigg |_0^{\infty} = \frac{\pi}{2a}

So, start with that one and differentiate:

.. math::

    \int_0^{\infty} \frac{\partial}{\partial a} \ \frac{1}{a^2 + x^2} \ dx = \frac{d}{da} \ \frac{\pi}{2a}

    - 2a \int_0^{\infty} \frac{1}{(a^2 + x^2)^2} \ dx = - \frac{\pi}{2a^2}
    
    \int_0^{\infty} \frac{1}{(a^2 + x^2)^2} \ dx = \frac{\pi}{4a^3}

    