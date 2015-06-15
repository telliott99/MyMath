.. _sum_n^2:

################
Sums of integers
################

The introduction to Riemann sums, which underlies the definition of integration, uses a standard example, the computation of the sum for :math:`x^2`.

For computing Riemann sums of powers of :math:`x` such as :math:`x^2`, we need formulas for the sums of integers from :math:`1 \Rightarrow N` as well as their squares, and cubes, etc.

.. math::

    \sum_{k=1}^N k^p, \ \ \ p = 1, 2, 3 \dots

========
Integers
========

There is a famous story about Gauss as a schoolboy, that he "saw" how to add the integers from :math:`1` to :math:`100` as two parallel sums

.. math::

    \ \  1 + \ \ 2 + \ \ 3 + \cdots + 99 + 100
    
    100 + 99 + 98 + \cdots + 2 + 1

Added together horizontally, these two series are clearly equal to twice the sum of :math:`1 \dots 100`.  But in the vertical columns, we notice that we have :math:`n` sums, each of which is equal to :math:`n+1`.  Writing this relationship as an equation:

.. math::

    2S = n (n+1)
    
    S = \frac{1}{2} \ n (n+1)
    
There is also famous "proof without words" for this.

.. image:: /figs/sum_n.png
       :scale: 25%

An interesting variation is to find the sum of the of odd integers

.. math::

    S = 1 + 3 + 5 + \dots 2n-1

which has a simple answer.  Note that the sums of the integers to :math:`2n` is

.. math::

    1 + 2 + 3 + 4 \dots 2n -1 + 2n = \frac{2n(2n + 1)}{2}

and the sum of the even integers in this range is:

.. math::
    
    2 + 4 + 6 + \dots + 2n = 2(1 + 2 + 3 \dots + n)
    
    = \frac{2(n)(n+1)}{2}
    
    = n(n+1)
    
The sum we seek is related:

.. math::
    
    S + n(n+1) = \frac{2n(2n + 1)}{2}
    
    = n(2n + 1) - n(n+1)
    
    = n^2

===================
Squares of Integers
===================

Next we develop the formula for the squares of integers.  It starts, oddly enough, from a cubic equation.  For any number it is certainly true that

.. math:: 

    (k + 1)^3 = k^3 + 3k^2 + 3k + 1

Writing this expression for every integer from :math:`1 \Rightarrow N`, and then summing them all, we obtain

.. math::

    \sum_{k=1}^N (k+1)^3 = \sum_{k=1}^N k^3 + \sum_{k=1}^N 3k^2 + \sum_{k=1}^N 3k + \sum_{k=1}^N 1

If we move :math:`\sum k^3` to the left-hand side, we obtain what is called a "telescoping sum"---only the first and the last terms survive:

.. math::

    \sum_{k=1}^N (k+1)^3 = (N+1)^3 + N^3 + (N-1)^3 + (N-2)^3 + \dots + 2

    \sum_{k=1}^N k^3 = N^3 + (N-1)^3 + (N-2)^3 + \dots + 2 + 1
    
    
Notice that the first sequence ends with :math:`2`.

.. math::
    
    \sum_{k=1}^N (k+1)^3 - \sum_{k=1}^N k^3 = (N+1)^3 - 1
    
So

.. math::

    (N+1)^3 - 1 = \sum_{k=1}^N 3k^2 + \sum_{k=1}^N 3k + \sum_{k=1}^N 1

The last sum is just :math:`N`, and we can bring a factor of three out from the others, so now we have:

.. math::

    (N+1)^3 - 1 = 3 \sum_{k=1}^N k^2 + 3 \sum_{k=1}^N k + N
    
Finally, we recall (from above) that the sum of the first :math:`N` integers is equal to :math:`N(N+1)/2` so 

.. math::

    (N+1)^3 - 1 = 3 \sum_{k=1}^N k^2 + 3 \frac{N (N+1)}{2} + N

Now it's just algebra---expand the cube:

.. math::

    N^3 + 3N^2 + 3N = 3 \sum_{k=1}^N k^2 + 3 \frac{N (N+1)}{2} + N
    
Gather the the terms other than the sum on one side:

.. math::

    N^3 + 3N^2 + 2N -  3 \frac{N (N+1)}{2}  = 3 \sum_{k=1}^N k^2

    N(N+1)(N+2) -  3 \frac{N (N+1)}{2}  = 3 \sum_{k=1}^N k^2
    
    \frac{N(N+1)(2N+4)}{2} -  3 \frac{N (N+1)}{2}  = 3 \sum_{k=1}^N k^2

    \frac{N(N+1)}{2} \ (2N + 4 - 3) = 3 \sum_{k=1}^N k^2

    \sum_{k=1}^N k^2 = \frac{N(N+1)}{2} \ \frac{(2N + 1)}{3}
    

There is a visual proof for this as well.

.. image:: /figs/sum_n2.png
       :scale: 50 %

++++++++++++++
Strang's proof
++++++++++++++

Here is one more approach.  It is from Strang's *Calculus*.  He says "the best place to start is a good guess".  So again, our goal is to find a formula for:

.. math::

    S = \sum_{k=1}^{n} \ k^2

Perhaps we visualize a pile of cannonballs

.. image:: /figs/cannonballs.png
       :scale: 50 %

Each layer contains a square number of cannonballs (:math:`1`, then :math:`4`, then :math:`9`, etc.).  The shape is a pyramid with dimensions :math:`n \times n \times n`.  We know the formula for the volume of a pyramid, and guess

.. math::

    S_n = \frac{1}{3} n^3

To test it, check whether this difference is :math:`n^2` (as it should be):

.. math::

    S_{n} - S_{n-1} = \frac{1}{3} n^3 - \frac{1}{3} (n-1)^3

Now

.. math::

    (n-1)^2 = n^2 - 2n + 1

    (n-1)^3 = (n-1)(n^2 - 2n + 1)

    = n^3 - 3 n^2 + 3 n - 1

So

.. math::

    S_{n} - S_{n-1} = \frac{1}{3} (n^3 - n^3 + 3 n^2 - 3 n + 1)

We see that our guess is off by the residual terms

.. math::

    \frac{1}{3} (3 n^2 - 3 n + 1)
    
    = n^2 - n + \frac{1}{3} 

Strang says:  the guess needs *correction terms*.

To cancel :math:`1/3` in the difference, subtract :math:`n/3` from the sum.  And to add back :math:`n` in the difference, add back :math:`1 + 2 + \dots + n(n+1)/2` to the sum.  Our new guess is

.. math::

    S_n =  \frac{1}{3} n^3 + \frac{n(n+1)}{2} - \frac{n}{3}
    
    = \frac{n}{6} (2n^2 + 3(n+1) - 2)
    
    =  \frac{n}{6} (2n + 1)(n + 1)
    
    = \frac{n(n+1)(2n+1)}{6}

which may be easier to remember as

.. math::

    S_n = \frac{n(n+1)}{2} \times \frac{2n + 1}{3}

=================
Cubes of Integers
=================

I won't go through it, but a very similar procedure will establish the formula for the cubes of integers.  It is remarkable:

.. math::

    \sum_{k=1}^N k^2 = (\frac{N(N+1)}{2})^2

