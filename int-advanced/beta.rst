.. _beta:

#############
Beta function
#############

We will follow the notation in Boas *Mathematical Methods in the Physical Sciences*.  The beta function is defined as:

.. math::

    B(p,q) = \int_0^1 x^{p-1} (1-x)^{q-1} \ dx, \ \ \  p > 0, \ q > 0

To change the range of integration, substitute

.. math::

    ax = y
    
    dx = \frac{1}{a} \ dy
    
    B(p,q) = \frac{1}{a} \int_0^a (\frac{y}{a})^{p-1} (1 - \frac{y}{a})^{q-1} \ dy

If we gather the :math:`a` terms we have:

.. math::

    a^{-1} \ a^{1-p} \ a^{1-q} = a^{(1-p-q)} = \frac{1}{a^{p + q - 1}}
    
and

.. math::

    B(p,q) = \frac{1}{a^{(p + q - 1)}} \int_0^a y^{p-1} (1-y)^{q-1} \ dy

To obtain the trigonometric form of the equation, let:

.. math::

    x = \sin^2 \theta
    
    1-x = \cos^2 \theta
    
    dx = 2 \sin \theta \cos \theta \ d \theta
    
So:

.. math::

    B(p,q) = \int_0^1 x^{p-1} (1-x)^{q-1} \ dx
    
    = \int (\sin^2 \theta)^{p-1} \ (\cos^2 \theta)^{q-1} \ 2 \sin \theta \cos \theta \ d \theta
    
The bounds are :math:`x = 0 \rightarrow 1` so :math:`\theta = 0 \rightarrow \pi/2` and

.. math::

    B(p,q) = 2 \int_0^{\pi/2} (\sin \theta)^{2p-1} (\cos \theta)^{2q-1} \ d \theta

We will use this in what follows.

==============
Beta and Gamma
==============

The relationship we will prove is:

.. math::

    B(p,q) = \frac{\Gamma(p) \ \Gamma(q)}{\Gamma(p+q)}

Recall that the definition of the :ref:`gamma function <gamma>` is:

.. math::

    \Gamma(p) = \int_0^{\infty} t^{p-1} e^{-t} \ dt

Let:

.. math::

    t = x^2
    
    dt = 2 x \ dx
    
    \Gamma(p) = \int_0^{\infty} (x^2)^{p-1} e^{-x^2} 2 x \ dx
    
    = 2 \int_0^{\infty} x^{(2p-1)} e^{-x^2} \ dx
    
:math:`x` and :math:`y` are both *dummy* variables in what follows, so we just write

.. math::

    \Gamma(q) = 2 \int_0^{\infty} y^{(2q-1)} e^{-y^2} \ dy

Multiplying together:

.. math::

    \Gamma(p) \ \Gamma(q) = 
    
    = 4 \int_0^{\infty} x^{(2p-1)} e^{-x^2} \ dx \ \int_0^{\infty} y^{(2q-1)} e^{-y^2} \ dy

    = 4 \int_0^{\infty} \int_0^{\infty} x^{(2p-1)} e^{-x^2} y^{(2q-1)} e^{-y^2} \ dx / dy
    
:math:`x` and :math:`y` are independent, so think of this as a double integral in the plane and switch to polar coordinates:

.. math::

    x = r \sin \theta, \ \ \ y = r \cos \theta

    = 4 \int_0^{\infty} \int_0^{\pi/2} (r \sin \theta)^{(2p-1)} \  (r \cos \theta)^{(2q-1)}  e^{-r^2} \ r \ dr \ d\theta
    
We have two parts here (the :math:`r` part and the :math:`\theta` part), and they are independent.  The first is:

.. math::

    \int_0^{\infty} r^{(2p-1)} r^{(2q-1)} r \ e^{-r^2} \ dr
        
    = \int_0^{\infty} r^{(2p + 2q -1)} \ e^{-r^2} \ dr

Recall that we had:

.. math::

    \Gamma(p) = 2 \int_0^{\infty} x^{(2p-1)} e^{-x^2} \ dx

If you compare these two expressions, equating the dummy variables :math:`r` and :math:`x`, and then looking at the exponents, substituting :math:`p+q` for `p` in the second one, we have that the :math:`r` part of the integral is equal to:

.. math::

    \frac{\Gamma(p+q)}{2} = \int_0^{\infty} r^{(2p + 2q -1)} \ e^{-r^2} \ dr

For the :math:`\theta` part of the integral (and leaving aside the factor of :math:`4` for a moment):

.. math::

    \int_0^{\pi/2} (\sin \theta)^{(2p-1)}  (\cos \theta)^{(2q-1)} / d\theta

If we look again at the trigonometric form of the beta function from above:

.. math::

    \frac{B(p,q)}{2} = \int_0^{\pi/2} (\sin \theta)^{2p-1} (\cos \theta)^{2q-1} \ d \theta

the :math:`\theta` part of our integral is identical.  Notice then that we have used up the factor of :math:`4` to cancel the two factors of one-half and we're left with just:

.. math::
    
    \Gamma(p+q) B(p,q) = \Gamma(p) \ \Gamma(q)

Thus, the relationship that we have derived is:

.. math::

    \frac{\Gamma(p) \ \Gamma(q)}{\Gamma(p+q)} = B(p,q)
    
    = \int_0^1 x^{p-1} (1-x)^{q-1} \ dx
    