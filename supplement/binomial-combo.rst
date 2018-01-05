.. _binomial-combo:

###############################
Binomial Theorem:  combinations
###############################

This section is a work in progress.  I found a proof of the binomial theorem by induction online here:

https://www.math.hmc.edu/calculus/tutorials/binomial_thm/induction.html

and a different one at wikipedia, but I couldn't follow all the steps.  (Some of them even seem invalid in the first one).

===================
Combinatorial proof
===================

In expanding 

.. math::

    (x + y)^3 = (x + y)(x + y)(x + y)
    
    = xxx + xxy + xyx + yxx + xyy + yxy + yyx + yyy

    = xxx + 3xxy + 3xyy + yyy

The coefficient of :math:`xxy` (for example) is :math:`3` precisely because in the equation:

.. math::

    (x + y)(x + y)(x + y)

for each term in parentheses we must choose either :math:`x` or :math:`y`, that is, not :math:`x`.

For the term :math:`x^{n-k}y^k`, there are exactly:

.. math::

    \frac{n!}{k!(n-k)!} = { n \choose k }

combinations that have :math:`n` elements of which :math:`k` are of the same type.  So here we have :math:`6/2 \times 1 = 3` possibilities.

It doesn't matter which type:  there will be the same number of terms with :math:`k` of :math:`x` and :math:`n-k` of y, versus :math:`n-k` of :math:`x` and :math:`k` of y.
