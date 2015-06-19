.. _hyperbolic:

##########################
Hyperbolic sine and cosine
##########################

===============
Sine and cosine
===============

Recalling Euler's formula (:ref:`here <euler-eqn>`):

.. math::

    e^{ix} = \cos x + i \sin x

.. math::

we obtain a similar formula with :math:`- ix`:

.. math::

    e^{-ix} = \cos(-x) + i\ \sin(-x) 
    
    = \cos x - i \ \sin x

Adding

.. math::

    e^{ix} +  e^{-ix} = 2 \cos x

    \cos x = \frac{1}{2} (e^{ix} +  e^{-ix})

and subtracting

.. math::

    e^{ix} -  e^{-ix} = 2 \ i \sin x
     
    \sin x =  \frac{1}{2i} (e^{ix} -  e^{-ix})

The usual properties can be shown.  For example (since :math:`e^{\theta} e^{\theta} = e^{2 \theta}` and :math:`e^{\theta} e^{-\theta} = 1`):

.. math::
     
    \sin^2 x = -\frac{1}{4} (e^{ix} -  e^{-ix})^2 = -\frac{1}{4} (e^{2ix} - 2 + e^{-2ix})
    
    \cos^2 x = \frac{1}{4} (e^{ix} +  e^{-ix})^2 = \frac{1}{4} (e^{2ix} +  2 +  e^{2-ix})
    
For :math:`\sin^2 x + \cos^2 x`, all the exponentials cancel, so we are left with

.. math::

    \sin^2 x + \cos^2 x = -\frac{1}{4}(-2) + \frac{1}{4}(2)
    
    = 1


===================
Hyperbolic versions
===================

The hyperbolic functions are defined similarly, but without i:

.. math::

    \cosh x = \frac{e^{x} +  e^{-x}}{2}

    \sinh x = \frac{e^{x} -  e^{-x}}{2i}

.. image:: /figs/cosh_and_sinh.png
   :scale: 50 %

The difference of squares has a simple value:

.. math::

    \cosh^2 t - \sinh^2 t = 1

Everything about the hyperbolic sine is reminiscent of the regular trig functions but with a sign change.

A plot of :math:`\sinh t` on the :math:`x`-axis and :math:`\cosh t` on the :math:`y`-axis yields a hyperbola in the same way the :math:`y^2 - x^2 = 1` does.

===========
derivatives
===========

.. math::

    \frac{d}{dx} 2 \sinh x = \frac{d}{dx} (e^x - e^{-x}) = e^x + e^{-x}  = 2 \cosh x

    \frac{d}{dx} 2 \cosh x = \frac{d}{dx} (e^x + e^{-x}) = e^x - e^{-x}  = 2 \sinh x

Also, note that: 

.. math::

    2 \sinh x + 2 \cosh x = 2 e^x

    e^x = \sinh x + \cosh x

Because of this, and by symmetry, we expect that the Taylor series expansions should be

.. math::

    \sinh x = x + \frac{x^3}{3!} + \frac{x^5}{5!} + \dots

    \cosh x = 1 + \frac{x^2}{2!} + \frac{x^4}{4!} + \dots

The values of the functions at zero are

.. math::

    \sinh 0 = 0

    \cosh 0 = 1

So, for example, the expansion for :math:`\sinh` is 

.. math::

    \sinh x = \sum_{n=0}^{\infty} \frac{f^n (0)\ x^n }{n!}

    = \frac{0 \cdot 1}{0!} + \frac{1 \cdot x}{1!} + \frac{0 \cdot x^2}{2!} + \frac{1 \cdot x^3}{3!} + \dots

and so on.

==========
Relativity
==========

The hyperbolic functions come into the mathematics of relativity, where for an observer in a moving reference frame, the following equations hold:

.. math::

    x' = \frac{x - vt}{\sqrt{1-v^2}}

    t' = \frac{t - vx}{\sqrt{1-v^2}}

The quantity :math:`s^2` is invariant where

.. math::

    s^2 = t^2 - x^2

Proof:

.. math::

    x'^2 = \frac{x^2 - 2xvt + v^2t^2}{1-v^2}

    t'^2 = \frac{t^2 - 2xvt + v^2x^2}{1-v^2}

    t'^2 - x'^2 = \frac{t^2 - x^2 + v^2x^2 - v^2t^2}{1-v^2}

    = \frac{t^2 - x^2 + v^2(x^2 - t^2) }{1-v^2}

    = \frac{t^2 - x^2 - v^2(t^2 - x^2) }{1-v^2}  = t^2 - x^2

The hyperbolic functions come in by defining a parameter :math:`\theta` (the "rapidity")

.. math::

    \cosh \theta = \frac{1}{\sqrt{1-v^2}}

Then

.. math::

    \sinh^2 \theta = \cosh^2 \theta - 1 = \frac{1}{1-v^2} - 1 = \frac{v^2}{1-v^2}

    \sinh \theta =  \frac{v}{\sqrt{1-v^2}}

So we can rewrite

.. math::

    x' = \frac{x - vt}{\sqrt{1-v^2}} = x \cosh \theta - t \sinh \theta

    t' = \frac{t - vx}{\sqrt{1-v^2}} = t \cosh \theta - x \sinh \theta

And the identity from above is

.. math::

    t'^2 - x'^2 = (t^2 \cosh^2 \theta - 2xt \sinh \theta \cosh \theta + x^2 \sinh^2 \theta)

    \ \ \ \ \ \ \ \ \ \ - (x^2 \cosh^2 \theta - 2xt \sinh \theta \cosh \theta + t^2 \sinh^2 \theta)

the terms starting with :math:`2xt` cancel and we have

.. math::

    t'^2 - x'^2 = (t^2 \cosh^2 \theta + x^2 \sinh^2 \theta - x^2 \cosh^2 \theta - t^2 \sinh^2 \theta)

    = t^2 (\cosh^2 \theta -  \sinh^2 \theta) - x^2  (\cosh^2 \theta -  \sinh^2 \theta)

    = t^2 - x^2

====
tanh
====

We had

.. math::

    \sinh \theta =  \frac{v}{\sqrt{1-v^2}}

    \cosh \theta = \frac{1}{\sqrt{1-v^2}}

so 

.. math::

    \tanh \theta = v

leading us to explore the properties of the hyperbolic tangent.  Going back to the beginning:

.. math::

    2 \sinh \theta = e^{\theta} -  e^{-\theta}

    2 \cosh \theta = e^{\theta} +  e^{-\theta}

    \tanh \theta = \frac{e^{\theta} -  e^{-\theta}}{e^{\theta} +  e^{-\theta}}

The derivative is (by the quotient rule):

.. math::

    \frac{d}{d\theta} \ \tanh \theta = \frac{\cosh^2 \theta - \sinh^2 \theta}{\cosh^2 \theta}

    =  \frac{1}{\cosh^2 \theta}

Shankar has a problem involving two angles

.. math::

    2 \sinh ( \theta + \phi) = e^{\theta + \phi} -  e^{-\theta - \phi}
    
    = e^{\theta} e^{\phi} - e^{-\theta} e^{- \phi}

===================
Inverse hyperbolics
===================

Having looked at the hyperbolic sine and cosine above:

.. math::

    y = \sinh x = \frac{1}{2} ( e^x - e^{-x} )

    y = \cosh x = \frac{1}{2} ( e^x + e^{-x} )

In many ways these are similar to sine and cosine with a sign difference.  For example

.. math::

    \cosh^2 x - \sinh^2 x = 1

    \frac{d}{dx} \sinh x = \cosh x

    \frac{d}{dx} \cosh x = \sinh x

Here, our first job is to derive the inverse functions.  To do that we must solve the above equations for :math:`x`.  Take the first one

===============
inverse of sinh
===============

.. math::

    y = \sinh x = \frac{1}{2} ( e^x - e^{-x} )

    x = \sinh^{-1} y

Substitute :math:`z=e^x`, then:

    2y = z - \frac{1}{z}

    z^2 - 2yz -1 = 0

Solve using the quadratic equation

.. math::

    z = \frac{2y \pm \sqrt{4y^2 + 4}}{2}

    = y \pm \sqrt{y^2 + 1}

Since :math:`z = e^x`, :math:`z > 0` so we take the positive root.  Substitute back to :math:`x`

.. math::

    e^x = y + \sqrt{y^2 + 1}

    x = \ln | y + \sqrt{y^2 + 1} |

Change back to the usual notation with :math:`y` as the dependent variable

.. math::

    y = \sinh^{-1} x = \ln | x + \sqrt{x^2 + 1} |

For the derivative

.. math::

    \frac{dy}{dx} = \frac{1}{x + \sqrt{x^2 + 1}} \ (1 + \frac{x}{\sqrt{x^2 + 1}} )

    = \frac{1}{x + \sqrt{x^2 + 1}} \ (\frac{\sqrt{x^2 + 1} + x}{\sqrt{x^2 + 1}} )

    = \frac{1}{\sqrt{x^2 + 1}}

    \frac{d}{dx} \sinh^{-1} x = \frac{1}{\sqrt{x^2 + 1}}

Recall that

.. math::

    \frac{d}{dx} \sin^{-1} x = \frac{1}{\sqrt{1 - x^2}}

Just a change of sign on one term. 

===============
inverse of cosh
===============

.. math::

    y = \cosh x = \frac{1}{2} ( e^x + e^{-x} )

    x = \cosh^{-1} y

As before, substitute :math:`z = e^x`

.. math::

    2y = z + \frac{1}{z}

    z^2 - 2yz + 1 = 0

    z = \frac{2y \pm \sqrt{4y^2 - 4}}{2}

    = y \pm \sqrt{y^2 - 1}

Take the positive root and back substitute

.. math::

    e^x = y + \sqrt{y^2 - 1}

    x = \ln | y + \sqrt{y^2 - 1} |

Change notation:

.. math::

    y = \cosh^{-1} x = \ln | x + \sqrt{x^2 - 1} |

Differentiate:

.. math::

    \frac{dy}{dx} = \frac{1}{x + \sqrt{x^2 - 1}} (1 + \frac{x}{\sqrt{x^2 - 1}}  )

    = \frac{1}{\sqrt{x^2 - 1}}

    \frac{d}{dx} \cosh^{-1} x = \frac{1}{\sqrt{x^2 - 1}}

Compare with 

.. math::

    \frac{d}{dx} \cos^{-1} x = -\frac{1}{\sqrt{1 - x^2}}

===============
inverse of tanh
===============

Start with 

.. math::

    y = \tanh x = \frac{e^x - e^{-x}}{e^x + e^{-x}}

    = \frac{e^x - 1/e^x}{e^x + 1/e^x}

Substitute :math:`z=e^x`, then:

.. math::

    y = \frac{z - 1/z}{z + 1/z}

    = \frac{z^2 - 1}{z^2 + 1}

    (y-1)z^2 + (0)z + (y+1) = 0

The quadratic equation gives:

.. math::

    \frac{\pm \sqrt{-4(y-1)(y+1)}}{2(y-1)}

Factor out the :math:`\sqrt{4}`

.. math::

    = \pm \frac{\sqrt{-(y-1)(y+1)}}{(y-1)}

    = \pm \frac{\sqrt{(1-y)(y+1)}}{(y-1)}

Choose the negative root but multiply on the bottom by :math:`-1`

.. math::

    = \frac{\sqrt{(1-y)(y+1)}}{(1-y)}

    = \frac{\sqrt{y+1}}{\sqrt{1-y}}

Substitute back

.. math::

    e^x = \frac{\sqrt{y+1}}{\sqrt{1-y}}

    x = \ln (\frac{\sqrt{y+1}}{\sqrt{1-y}})

    x = \frac{1}{2} \ln (\frac{y+1}{1-y})

Change notation

.. math::

    y = \tanh^{-1} x = \frac{1}{2} \ln (\frac{x+1}{1-x})

Differentiate

.. math::

    \frac{d}{dx} \tanh^{-1} x = (\frac{1}{2}) \frac{1-x}{x+1} \frac{(1-x + x + 1)}{(1-x)^2}

    = \frac{1-x}{(x+1)(1-x)^2}

    = \frac{1}{(x+1)(1-x)}

    = \frac{1}{1-x^2}
