.. _trig:

##############
Trig Integrals
##############

If we have two functions :math:`F(x)` and :math:`f(x)` where

.. math::

    \frac{d}{dx} F(x) = F'(x) = f(x)

then the fundamental theorem of calculus (:ref:`FTC <ftc>`) says that

.. math::

    \int f(x) \ dx = F(x) + C

Let's go through the standard trigonometric functions to find their derivatives and integrals.

Back :ref:`here <trig_derivatives>`, we found the derivatives of sine and cosine.

===============
Sine and cosine
===============

.. math::

    \frac{d}{dx} \sin x = \cos x; \ \ \ \int \cos x \ dx = \sin x

    \frac{d}{dx} \cos x = -\sin x; \ \ \ \int \sin x \ dx = -\cos x

=======
Tangent
=======

The next one is the tangent.  For the derivative, use the quotient rule:

.. math::

    \frac{d}{dx} \ \frac{\sin x}{\cos x} = \frac{\cos^2 x - (-\sin^2 x)}{\cos^2 x} = \sec^2 x
    
    \frac{d}{dx} \tan x = \sec^2 x; \ \ \ \int \sec^2 x \ dx = \tan x

The integral is easy by U-substitution:

.. math::

    \int \frac{\sin x}{\cos x} \ dx = - \ln | \cos x | + C
    
======
Secant
======

We obtained the secant-squared above in differentiating the tangent.  How about the secant?

When faced with 

.. math::

    \int \sec x \ dx
    
somebody (Isaac Barrow) once had a wild idea!  Multiply and divide by :math:`\tan x + \sec x`:

.. math::

    \int \sec x \ \frac{\tan x + \sec x}{\tan x + \sec x}  \ dx

    =  \int \frac{\sec x \ \tan x + \sec^2 x}{\sec x + \tan x}  \ dx

https://en.wikipedia.org/wiki/Integral_of_the_secant_function

Recall that the derivative of :math:`\tan x` is :math:`\sec^2 x` and the derivative of :math:`\sec x` is :math:`\sec x \tan x`.

Our clever construction has produced an expression

.. math::

    \int \frac{\sec x \ \tan x + \sec^2 x}{\sec x + \tan x}  \ dx

in which the numerator is the derivative of the denominator.  This is just
 
.. math::
 
    \int \frac{1}{u} \ du = \ln |u|

    = \ln |\sec x + \tan x|
    
plus :math:`C`, of course.

We can certainly check that.

.. math::

    \frac{d}{dx} \ln |\sec x + \tan x|
    
    = \frac{1}{\sec x + \tan x} \ (\sec x \tan x + \sec^2 x)

    = \sec x \ \frac{\tan x + \sec x}{\sec x + \tan x}

    = \sec x

