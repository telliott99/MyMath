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


