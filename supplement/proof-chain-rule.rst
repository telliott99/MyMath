.. _proof-chain-rule:

#######################
Proof of the chain rule
#######################

Given two functions :math:`f` and :math:`g` we are interested in the composite function :math:`f(g(x))`, often written as :math:`f \circ g`, and in particular, we wish to derive an expression for the derivative.  

As always, we need to compute the limit of the difference quotient:

.. math::

    \frac{d}{dx} \ (f \circ g) = \lim_{h \rightarrow 0} \frac{f(g(x+h)) - f(g(x))}{h}
    
Naturally, we insist that :math:`g` be differentiable at :math:`x` and :math:`f` be differentiable at the point given by :math:`g(x)`.

The chain rule is a simple formula:

.. math::

    \frac{d}{dx} \ (f \circ g) = f'(g(x)) \cdot g'(x)
    
which is perhaps more easily remembered as

.. math::

    \frac{df}{dx} = \frac{df}{dg} \ \frac{dg}{dx}

As an example, if we write

.. math::

    y = g(x) = x^2
    
    z = f(y) = y^2
    
    z' = 2y \cdot 2x = 2(x^2) 2 x = 4 x^3

which is easily checked by recognizing that :math:`z = x^4`.

Or write it implicitly as

.. math::

    dy = 2x \ dx

    dz = 2y \ dy 
        
    = 2 y \ 2 x \ dx 
    
    = 4 x^2 x \ dx
    
    \frac{dz}{dx} = 4 x^3

===============
Intuitive proof
===============

http://www.askamathematician.com/2012/03/q-is-there-an-intuitive-proof-for-the-chain-rule/
    
=====
Proof
=====

from:

http://kruel.co/math/chainrule.pdf
    
The proof is a little tedious, but it is mainly a question of bookkeeping.  Here goes.  

Again, we want to compute the limit of the difference quotient:

.. math::

    \lim_{h \rightarrow 0} \frac{f(g(x+h)) - f(g(x))}{h}
    
Since :math:`g(x)` is differentiable at :math:`x`

.. math::

    g'(x) = \lim_{h \rightarrow 0} \frac{g(x+h) - g(x)}{h}
    
Rearrange and define a new variable :math:`v`

.. math::

    v = \frac{g(x+h) - g(x)}{h} - g'(x)

We do this so we won't have to keep writing these terms as we do some algebra.  In the end, we will make :math:`v` go away by noting that :math:`v` depends on :math:`h` and :math:`v \rightarrow 0` as :math:`h \rightarrow 0` (the limit of the difference quotient is equal to the derivative :math:`g'(x)` by definition).  

We can set up a similar expression involving :math:`f`, namely:

.. math::

    w = \frac{f(y+k) - f(y)}{k} - f'(y)
    
:math:`w` depends on :math:`k` and :math:`w \rightarrow 0` as :math:`k \rightarrow 0`.

Rearrange some more:

.. math::

    g(x+h) = g(x) + [ \ g'(x) + v \ ] \ h
    
    f(y+k) = f(y) + [ \ f'(y) + w \ ] \ k
    
+++++++
Rewrite
+++++++

So now we want to rewrite :math:`f(g(x+h))` to be :math:`f(g(x)) +` stuff.  Using the first equation

.. math::

    g(x+h) = g(x) + [ \ g'(x) + v \ ] \ h

rewrite :math:`f(g(x+h))`:

.. math::

    f(g(x+h)) = f(g(x) + [ \ g'(x) + v \ ] \ h )

Now, let us pick a particular value for :math:`k`

.. math::

    k = \ [ \ g'(x) + v \ ] \ h
    
Notice that as :math:`h \rightarrow 0`, so :math:`k \rightarrow 0`.

Substituting this value of :math:`k`, we have

.. math::

    f(g(x+h)) = f(g(x) + k)

Now, using the second equation:

.. math::
    
    f(y+k) = f(y) + [ \ f'(y) + w \ ] \ k

substitute on the right-hand side, giving:

.. math::
    
    f(g(x + h)) = f(g(x)) + [ \ f'(g(x)) + w \ ] \ k
    
substituting back for :math:`k`:

.. math::

    f(g(x+h)) = f(g(x)) + [ \ f'(g(x)) + w \ ] \ [ \ g'(x) + v \ ] \ h

Now that we have extracted :math:`f(g(x))` from :math:`f(g(x+h))`, we can put everything together and see some cancellation.

+++++++++++++++++++
Difference quotient
+++++++++++++++++++

Go back to the difference quotient:

.. math::

    \frac{f(g(x+h)) - f(g(x))} { h }

substitute the expression for :math:`f(g(x+h))` from above:
    
.. math::
    
    = \frac{f(g(x)) + \ [ \ f'(g(x)) + w \ ] \ \ [ \ g'(x) + v \ ] \ [ \ h \ ] \ - f(g(x))}{h}
    
Cancel the first and last term in the numerator

.. math::

    = \frac{[ \ f'(g(x)) + w \ ] \ \ [ \ g'(x) + v \ ] \ [ \ h \ ]}{h}
    
Cancel the :math:`h`

.. math::
    
    = [ \ f'(g(x)) + w \ ] \ \ [ \ g'(x) + v \ ]

So now, we just need to take it to the limit:

.. math::
    
    = \lim_{h \rightarrow 0} \ [ \ f'(g(x)) + w \ ] \ \ [ \ g'(x) + v \ ]
    
    = \ [  \ \lim_{h \rightarrow 0} f'(g(x)) +  \lim_{h \rightarrow 0} w \ ] \ [ \  \lim_{h \rightarrow 0} g'(x) +  \lim_{h \rightarrow 0} v \ ]

But, as :math:`h \rightarrow 0`, so :math:`k \rightarrow 0`, and :math:`v \rightarrow 0`.  Also, as :math:`k \rightarrow 0` so :math:`w \rightarrow 0`.  That means we just have:

.. math::

    = \lim_{h \rightarrow 0} f'(g(x)) \cdot \lim_{h \rightarrow 0} g'(x)
    
    = f'(g(x)) \cdot g'(x)
    
which is the chain rule.