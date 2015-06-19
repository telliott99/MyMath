.. _mvt:

##################
Mean value theorem
##################

A man passes a police car at point :math:`A` doing :math:`60` mph (the speed limit) and 4 minutes later passes another police car at point :math:`B`, also doing :math:`60` mph, yet the second officer writes him a ticket for speeding, justified by the mean value theorem.  The reason:  point :math:`A` and point :math:`B` are 5 miles apart, hence the average speed over this interval was 75 mph, and *must at least have been equaled at some point*.

If :math:`f` is a "nice" function on the interval :math:`(a,b)` then there exists at least one point :math:`c` in that interval where

.. math::

    f'(c) = \frac{f(b) - f(a)}{b-a}

.. image:: /figs/mvt.png
   :scale: 50 %

==============
Nice functions
==============

What does it take to be "nice"?  The function :math:`f` must be continuous over the closed interval :math:`[a,b]` and differentiable over the open interval :math:`(a,b)`.

===============
Rolle's Theorem
===============

Rolle's Theorem says that for a "nice" :math:`f`, if :math:`f(a) = f(b)`, then there will exist at least one point :math:`c` in the interval :math:`(a,b)` such that :math:`f'(c) = 0`.

from the *Lifesaver*

    To do this, we use the Max-Min Theorem to say that if :math:`f` has a global maximum and a global minimum in if :math:`[a, b]`.
    
    If either the maximum or the minimum occurs at some number if :math:`c` in if :math:`(a,b)`, then the Extreme Value Theorem says that if :math:`f′(c) = 0`. (We know that if :math:`f′(c)` exists since if :math:`f` is differentiable in if :math:`(a, b)`.)
    
    The only other possibility is that the global maximum and the global minimum both occur at the endpoints if :math:`a` and if :math:`b`. In that case, since if :math:`f(a) = f(b)`, the function must be constant, so every number if :math:`c` in if :math:`(a,b)` satisfies if :math:`f′(c) = 0`. That’s all there is to the proof!

Here are some examples where the theorem applies:

.. image:: /figs/Rolle1.png
   :scale: 50 %

.. image:: /figs/Rolle2.png
  :scale: 50 %

And here are some examples where the theorem does not apply:

.. image:: /figs/Rolle3.png
   :scale: 50 %

.. image:: /figs/Rolle4.png
  :scale: 50 %

==================
Mean Value Theorem
==================

The MVT relies on Rolle's Theorem, which is similar.  The MVT proof basically turns Rolle's interval so that :math:`a \ne b`.

Consider the :math:`f(x)` from Rolle's Theorem above.  Define a new function

.. math::

    g(x) = f(x) - \frac{f(b) - f(a)}{b-a} \ (x-a)

from the *Lifesaver*

    It looks a little complicated, but actually all we are doing is subtracting a constant multiple of the linear function (x − a) from f(x) and calling it g. So the function g is also continuous on [a, b] and differentiable on (a, b), and what’s more, we have

(substituting :math:`a` or :math:`b` for :math:`x`):
    
.. math::

    g(a) = f(a) - \frac{f(b) - f(a)}{b-a} \ (a-a) = f(a)

    g(b) = f(b) - \frac{f(b) - f(a)}{b-a} \ (b-a) = f(a)
    

So

    we have shown that :math:`g(a) = g(b)`, which means we can apply Rolle’s Theorem! We end up with a number :math:`c` such that :math:`g′(c) = 0`. Now we just have to differentiate :math:`g` and see what that means for :math:`f`. Since the quantities :math:`f(b)−f(a)` and :math:`b − a` are constant, we get
    
.. math::

    g(x) = f(x) - \frac{f(b) - f(a)}{b-a} \ (x-a)

    g'(x) = f'(x) - \frac{f(b) - f(a)}{b-a}
    
Now plug in :math:`x=c`.  Since :math:`g'(c) = 0`:

.. math::

    0 = f'(c) - \frac{f(b) - f(a)}{b-a}

    f'(c) = \frac{f(b) - f(a)}{b-a}


