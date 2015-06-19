.. _trig_derivatives:

#########################
Trigonometric derivatives
#########################

The two fundamental trigonometric derivatives are:

.. math::

    \frac{d}{dx}\sin x = \cos x
    
    \frac{d}{dx}\cos x = -\sin x

====
Sine
====

The first of these comes from analyzing the difference quotient

.. math::

    \lim_{h \rightarrow 0} \frac{\sin (x + h) - \sin x}{h}

using the sum formula for sine (derived :ref:`here <cosine_s+t>`):

.. math::

    \sin(x+h) = \sin x \cos h + \sin h \cos x

we obtain

.. math::

    \lim_{h \rightarrow 0} \frac{\sin x \cos h + \sin h \cos x - \sin x}{h}

rearranging

.. math::

    \lim_{h \rightarrow 0} \frac{\sin x( \cos h - 1)}{h} + \frac{\sin h \cos x}{h}

and since 

.. math::

    \lim_{h \rightarrow 0} \frac{\sin h}{h} = 1

(as shown :ref:`here <lim_x_sinx>`), the limit of the right-hand term  is :math:`\cos x`.  The limit of :math:`\cos h - 1/h` is shown below, but it is equal to :math:`0`, so the whole limit is :math:`0`.

.. math::

    \lim_{h \rightarrow 0} \sin h/h

above is justifiably famous.  The second limit (:math:`\cos h - 1/h`) can be derived from the first:

.. math::

    \lim_{h \rightarrow 0}  \frac{\cos h - 1}{h} \times\frac{\cos h + 1}{\cos h + 1}

    =  \lim_{h \rightarrow 0}  \frac{\cos^2 h - 1}{h (\cos h + 1)}

    =  \lim_{h \rightarrow 0}  \frac{- \sin h}{h}  \times \frac{\sin h}{\cos h + 1}
    
The left-hand term is :math:`-1` (as above) and the right-hand term is :math:`0/2 = 0`.

======
Cosine
======

The derivative of the cosine can also be obtained by using the difference quotient, but why don't we just try :ref:`implicit differentiation<implicit-diff>` plus the previous result:

.. math::
    
    \sin^2 x + \cos^2 x = 1

    \frac{d}{dx} (\sin^2 x + \cos^2 x) = 0

    2 \sin x \frac{d}{dx} \sin x + 2 \cos x \frac{d}{dx} \cos x = 0

    2 \sin x \cos x + 2 \cos x \frac{d}{dx} \cos x = 0

    \sin x +  \frac{d}{dx} \cos x = 0

You can see how this turns out!

The difference quotient approach gives:

.. math::

    \lim_{h \rightarrow 0} \frac{\cos (x + h) - \cos x}{h}

From the addition rule for cosine (:ref:`here <cosine_s+t>`):

.. math::

    = \lim_{h \rightarrow 0} \frac{\cos x \cos h - \sin x \sin h - \cos x}{h}

    = \lim_{h \rightarrow 0} \frac{\cos x (\cos h - 1) - \sin x \sin h }{h}
    
    = \lim_{h \rightarrow 0} \frac{\cos x (\cos h - 1)}{h} - \frac {\sin x \sin h }{h}

The second term contains our famous limit :math:`\sin h / h = 1` (as :math:`h \rightarrow 0`);  so that term is just equal to :math:`- \sin x`.  The limit for the first term is

.. math::

    = \lim_{h \rightarrow 0} \frac{\cos h - 1}{h}
    
This is the second limit from the section above on sine, which is equal to zero.  So the first term drops out and we have in the end just

.. math::

    \lim_{h \rightarrow 0} \frac{\cos (x + h) - \cos x}{h} = - \sin x
    
+++++++
Example
+++++++

Example using the product rule:

.. math::

    f(x) = x \sin x
    
    f'(x) = x \cos x + \sin x
    
and

.. math::

    f(x) = \sin x \cos x
    
    f'(x) = -\sin^2x + \cos^2x 
    
    = 2 \cos^2x - 1

Later, when we want to go backward from the derivative :math:`\cos^2 x` or :math:`\sin^2 x` to the original function (i.e. integration), this second result will become very useful.

==================
Tangent and secant
==================

What about other functions like :math:`\tan x` and :math:`\sec x`?  We use the quotient rule.

.. math::

    (\frac{u}{v})' = \frac{u'v - uv'}{v^2}

I check this mentally by considering :math:`1/x`.  We pick up a minus sign from :math:`-uv'`, which is what we want, so this is correct.

Or alternatively, use :math:`x/1` !!  We do not get a minus sign from :math:`u'v`, so again, this is correct.

For :math:`\tan x` we have:

.. math::

    \frac{u}{v} = \frac{\sin x}{\cos x}

    (\frac{u}{v})' = \frac{\cos^2x + \sin^2x}{\cos^2x} 
    
    = \frac{1}{\cos^2x} = \sec^2x

Probably the most important of the rest is the secant:

.. math::

    \frac{d}{dx} \sec x

    = \frac{d}{dx} \frac{1}{\cos x} 
    
    = \frac{- (-\sin x)}{\cos^2 x}

    = \sec x \tan x

========
The rest
========

We can use the quotient rule for these too, or we can just memorize them by their the following pattern:  they are similar to their friends, but with a minus sign.

.. math::

    \frac{d}{dx} \csc x =  -\csc x \cot x

    \frac{d}{dx} \sec x =  \sec x \tan x 

and

.. math::

    \frac{d}{dx} \cot x =  -\csc^2 x

    \frac{d}{dx} \tan x =  \sec^2 x

If these are (perhaps) too hard to remember, they are easy enough to derive with the quotient rule.  They come in handy for evaluating various kinds of integrals.

