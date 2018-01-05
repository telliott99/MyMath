.. _LHopital:

################
L'Hopital's rule
################

Suppose we have two functions :math:`f(x)` and :math:`g(x)`, and we are interested in what value their ratio takes on in some limit (as :math:`x \rightarrow a`):

.. math::

    \lim_{x \rightarrow a} \frac{f(x)}{g(x)}

l'Hopital's Rule says that *if* the limits for the individual functions are both :math:`0`, then

.. math::

    \lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \lim_{x \rightarrow a} \frac{f'(x)}{g'(x)}

if the limit exists.  Sometimes it happens that the rule must be applied a second time (or even a third) and that is OK.

Note:  the rule can also be applied when both limits approach :math:`\infty`.  That works because:

.. math::

    \lim_{x \rightarrow a} \frac{f(x)}{g(x)} = \lim_{x \rightarrow a} \frac{1/g(x)}{1/f(x)}

The ratio has the indeterminate limit :math:`0/0` and the rule applies.

A great example is the use of l'Hopital's Rule is:

.. math::

    \lim_{x \rightarrow 0} \frac{1-\cos x}{x}

Both numerator and denominator individually tend to :math:`0` in the limit.  So we can use the rule:  

.. math::

    \lim_{x \rightarrow 0} f'(x) = \lim_{x \rightarrow 0} \sin x = 0

    \lim_{x \rightarrow 0} g'(x) = \lim_{x \rightarrow 0} 1 = 1

So the ratio is equal to zero, in the limit.

We saw this one (actually, its negative) in computing the difference quotient for sine.

Suppose

.. math::

    \frac{f}{g} = \frac{\tan x}{\sin x}

Both tend to :math:`0` in the limit as :math:`x \rightarrow 0`.  So

.. math::

    \frac{f'}{g'} = \frac{\sec^2 x}{\cos x}

At :math:`x=0` the limit is :math:`1/1`.

For a great discussion of the l'Hopital's rule, and the mean value theorem, with proofs, see Strang Chapter 3, section 8.



