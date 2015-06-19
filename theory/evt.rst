.. _evt:

#####################
Extreme value theorem
#####################

===============
Min-max theorem
===============

Before getting to the Extreme Value Theorem, we start with the Min-max theorem.  This one says that:

    if :math:`f` is continuous on :math:`[a,b]` then :math:`f` has at least one maximum and one minimum on :math:`[a,b]`.
    
Seems fairly obvious.

Here are some examples where the theorem applies:

.. image:: /figs/min-max1.png
   :scale: 50 %

.. image:: /figs/min-max2.png
  :scale: 50 %

And here are some examples where the theorem does not apply:

.. image:: /figs/min-max3.png
   :scale: 50 %

.. image:: /figs/min-max4.png
  :scale: 50 %

=====================
Extreme Value Theorem
=====================

The Extreme Value Theorem says that if :math:`x = c` is a local maximum or minimum for a function :math:`f`, then :math:`x = c` is a critical point for :math:`f`. This means that either :math:`f′(c)` doesn’t exist, or :math:`f′(c) = 0`.
    
    To prove this, let’s first suppose that :math:`x = c` is a local minimum for :math:`f`. If :math:`f′(c)` doesn’t exist, then it’s a critical point, which is exactly what we were hoping for. On the other hand, if :math:`f′(c)` exists, then

.. math::

    f'(c) = \lim_{h \rightarrow 0} \frac{f(c+h) - f(c)}{h}
    
.

    Since :math:`c` is a local minimum, we know that :math:`f(c + h) ≥ f(c)` when :math:`c + h` is very close to :math:`c`. Of course, :math:`c+h` is close to :math:`c` exactly when :math:`h` is close to :math:`0`. For such :math:`h`, the numerator :math:`f (c + h) − f (c)` in the above fraction must be nonnegative. When :math:`h > 0`, the quantity
    
.. math::

    \frac{f(c+h) - f(c)}{h}

.

    is positive (or :math:`0`), but when :math:`h < 0`, the quantity is negative (or :math:`0`). So the right-hand limit
    
.. math::

    \lim_{x \rightarrow c+} \ \frac{f(c+h) - f(c)}{h}

.

    must be greater than or equal to :math:`0`, while the same left-hand limit is less than or equal to :math:`0`. Since the two-sided limit exists, the left-hand and right-hand limits are equal; the only possibility is that they are both :math:`0`. This shows that :math:`f′(c) = 0`, so :math:`x = c` is once again a critical point for :math:`f`.
    
    How about if :math:`x = c` is a local maximum? I leave it to you to repeat the argument. The only difference is that the quantity :math:`f(c + h) − f(c)` is now negative (or :math:`0`) when :math:`h` is close to :math:`0`.