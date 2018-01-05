.. _euler-factorial:

##########################
Euler's Factorial Integral
##########################

The formula is:

.. math::

    n! = \int_0^{\infty} t^n e^{-t} \ dt

(:math:`n \ge 0`).  Let's see if this gives correct answers.

For :math:`n = 0` we have:

.. math::

    \int_0^{\infty} e^{-t} \ dt
        
As usual, we first imagine :math:`t` very large at the upper bound and then find the limit as :math:`t \rightarrow \infty`.  Here, we obtain

.. math::

    = -e^{-t} \ \bigg |_0^{\infty}
    
    = 0 - (-1) = 1
    
For reference, the result is that:

.. math::

    \int_0^{\infty} e^{-t} \ dt = 1

For :math:`n = 1` we have:

.. math::

    \int_0^{\infty} t e^{-t} \ dt

We solve this using integration by parts:

.. math::

    u = t, \ \ \ du = dt
    
    dv =  e^{-t} \ dt
    
    v = -e^{-t}
    
So the integral is:

.. math::

    = -t e^{-t} + \int_0^{\infty} e^{-t} \ dt

The second term is our previous result and the first term is:

.. math::
    
    = -t e^{-t} \ \bigg |_0^{\infty}

At the lower bound, this term is zero.  Now we must evaluate:

.. math::

    \lim_{t \rightarrow \infty} -t e^{-t}

    = \lim_{t \rightarrow \infty} \frac{-t}{e^{t}} = \frac{- \infty}{\infty}
    
So we use :ref:`L'Hopital <LHopital>` and differentiate:

.. math::

    = \lim_{t \rightarrow \infty} \frac{-1}{e^{t}} = \frac{-1}{\infty} = 0

Therefore, this term is equal to zero and the result of the integral is just equal to :math:`1`.

============
Generalizing
============

The general case is:

.. math::

    \int_0^{\infty} t^n e^{-t} \ dt

As before, we use integration by parts:

.. math::

    u = t^n, \ \ \ du = n t^{n-1} \ dt
    
    dv =  e^{-t} \ dt
    
    v = -e^{-t}
    
So the integral is:

.. math::

    = -t^n e^{-t} + n \int t^{n-1} e^{-t} \ dt
    
The first term is analyzed as we did above.  

We need to apply the rule repeatedly (:math:`n` times), and eventually find that the result is zero at the upper bound as well as the lower bound.

The second term is :math:`n` times the result for :math:`f(n-1)`.  Recalling that we had :math:`f(0) = f(1) = 1`, we find that:

.. math::

    \int_0^{\infty} t^n e^{-t} \ dt = n!


    