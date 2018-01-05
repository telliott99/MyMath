.. _exp-irrational:

##########################
Proof that e is irrational
##########################

I found a nice proof of this in the calculus text by Courant and Robbins.  

It is a proof by contradiction.  We start by assuming that :math:`e` is rational.

.. math::

    e = \frac{p}{q}, \ \  p,q \in \mathbb{N}

We make use of the infinite series representation of :math:`e`

.. math::

    e = \sum_0^{\infty} \frac{1}{n!}
    
    = 1 + 1 + \frac{1}{2!}  + \frac{1}{3!} + \frac{1}{4!} + \cdots

From this, it is obvious that :math:`e > 2`.  If you're interested, there is a proof that :math:`e < 3` in the book.

Here is a simple argument:  the series above after the first two terms is:

.. math::

    \frac{1}{2} + \frac{1}{6} + \frac{1}{24} + \dots

This series is smaller, term by term, than the geometric series with :math:`r=1/2`, which sums to :math:`1`.  Therefore, this sum must be less than :math:`1` and so :math:`e < 3`.
    
Now, if :math:`e = p / q` with :math:`p` and :math:`q` integers, and 

.. math::

    2 < e < 3
    
then :math:`p \notin \{1,2,3\}`, so :math:`p >= 4`, and therefore :math:`q > 1`,  so :math:`q >= 2`.

Having established this point, equate the series representation to the rational fraction :math:`p/q`:

.. math::

    \frac{p}{q} = 1 + 1 + \frac{1}{2!}  + \frac{1}{3!} + \frac{1}{4!} + \cdots

Multiply both sides by :math:`q!`.  For the left-hand side, we have

.. math::

    e \ q! = \frac{p}{q} \ q! = p (q-1)!

We won't need to do anything more with this, but simply note that since :math:`e\ q!` is equal to :math:`p (q-1)!`, the left-hand side must be an integer.

Therefore, the right-hand side must also be an integer.  This is the series

.. math::

    q! + q! + \frac{q!}{2!}  + \frac{q!}{3!}  + \cdots + \frac{q!}{(q-1)!} + \frac{q!}{q!} + \frac{q!}{(q+1)!} + \cdots

Now, :math:`q!` is obviously an integer. And for every integer :math:`k < q`, :math:`k!` divides :math:`q!` evenly 

.. math::

    \frac{q!}{k!} = q \times (q-1) \times (q-2) \cdots \times (q-k+1)

In the series

.. math::

    q! + q! + \frac{q!}{2!}  + \frac{q!}{3!}  + \cdots + \frac{q!}{(q-1)!} + \frac{q!}{q!} + \frac{q!}{(q+1)!} + \cdots

all the terms to the left of :math:`q!/(q-1)!` are integers, as is :math:`q!/(q-1)! = q` and :math:`q!/q! = 1`.

So now our concern is with the fractions that follow.  We will show that these sum to something less than :math:`1`.  We have

.. math::

    \frac{1}{(q+1)} + \frac{1}{(q+1)(q+2)} + \frac{1}{(q+1)(q+2)(q+3)} + \cdots

.. math::

Since :math:`q >= 2`

.. math::

    \frac{1}{(q+1)} <= \frac{1}{3}

    \frac{1}{(q+1)(q+2)} <= (\frac{1}{3})^2

and so on, and the entire remaining series of fractions is less than or equal to

.. math::

    \frac{1}{3} + (\frac{1}{3})^2 + (\frac{1}{3})^3 + \cdots

This is the geometric series with :math:`r = 1/3` and first term equal to :math:`r`, and the sum is known to be

.. math::

    \frac{1/3}{1-1/3} = \frac{1}{2}

Since the right-hand side is equal to an integer plus something "less than or equal to :math:`1/2`", it is not an integer, and cannot be equal to the left-hand side, which is equal to an integer.  We have reached a contradiction.  Therefore :math:`e` cannot be equal to :math:`p/q`, for :math:`p,q \in \mathbb{N}`.