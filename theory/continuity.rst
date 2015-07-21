.. _continuity:

##########
Continuity
##########

Continuity has an intuitive definition:  we should be able to graph the function *without lifting the pencil from the paper*.  Basically, we require that for a function to be continuous at a point :math:`x=a`, if we move :math:`x` away from :math:`a` by a little bit, then :math:`f(x)` should not change from :math:`f(a)` by too much.  

A formal definition uses the apparatus of limits:  epsilons and deltas.  We implement this backwards (as usual) by specifying how small a change in :math:`f(x)` we will allow, call it (:math:`\epsilon`).

A function :math:`f(x)` is continuous at :math:`x = a` if, for any :math:`\epsilon > 0`, however small, we can find a :math:`\delta` such that:
    
.. math::

    |f(x) - f(a)| < \epsilon \text{ for } |x - a| < \delta

Not only must the function approach the same limit as :math:`x \rightarrow a` from either side, but that limit must be equal to :math:`f(a)`.

=================
Differentiability
=================

A particularly easy way to answer the question "is my function continuous at :math:`x=a`" is to ask whether it is differentiable at :math:`x=a`.  The reason is the following theorem:

    If a function is differentiable at :math:`x`, then it is continuous at :math:`x`.

Here is the proof of this theorem from the *Lifesaver*.  A semi-official statement of continuity (with no delta or epsilon) is that if

.. math::

    \lim_{h \to 0}f(x + h) = f(x)

then :math:`f` is continuous at :math:`x`.  And that seems perfectly clear.
So how do we get there?  For starters, notice what we're given as known, namely, that the limit

.. math::

    f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}

exists.  That's what the first part of the theorem states as *given*.  And since :math:`f'(x)` exists, we know that :math:`f(x)` exists, otherwise this limit would be nonsense.

OK.  Now for the proof.  Consider

.. math::

    \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}  \times h

We know that this limit exists.  Why?  Because we can use the product rule for limits to split it into two parts

.. math::

    \lim_{h \to 0} \frac{f(x+h) - f(x)}{h} \times \lim_{h \to 0} h

The product of these two factors is 

.. math::

    f'(x) \times \lim_{h \to 0} h = f'(x) \times 0 = 0

So the limit exists, and its value is :math:`0`.

On the other hand, we can cancel the :math:`h` from the first expression, obtaining

.. math::

    \lim_{h \to 0} f(x+h) - f(x)

and since we showed that the first limit exists (and is equal to zero), this second one must exist as well (and still be equal to zero).  Let's see what more we can do with this.  We can split the limit into two parts:

.. math::

    \lim_{h \to 0} f(x+h) - \lim_{h \to 0} f(x)

but :math:`h` is not involved in the second term so

.. math::

    \lim_{h \to 0} f(x+h) - f(x)

Now, we know that this whole thing is equal to :math:`0`

.. math::

    \lim_{h \to 0} f(x+h) - f(x) = 0

Put :math:`f(x)` on the right-hand side, and we're done.

Remember though, that continuity does *not* imply differentiability.  A simple counterexample is the absolute value function at :math:`x=0`.  The function is continuous, but the slope at :math:`x=0` does not exist (because the slopes coming in from the two directions are not the same).

