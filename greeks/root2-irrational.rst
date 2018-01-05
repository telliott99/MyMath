.. _root2-irrational:

################
Square root of 2
################

A member of the Pythagorean school, whose name is lost to history, proved that there is no rational number :math:`p/q` (where :math:`p` and :math:`q` are integers) such that :math:`(p/q)^2 = 2`.  

We say that :math:`\sqrt{2}` is irrational because no such rational number :math:`p/q` exists.

+++++++++++++++++++++++
Squares of even and odd
+++++++++++++++++++++++

Before we begin the proof we need to establish a property of squares of integers.  The square of an even integer is always even, and the square of an odd integer is always odd.

We can write any *even* integer :math:`2,4,6 \dots` as 

.. math::

    e = 2k

for :math:`k \in \{1,2,3 \dots\}`.  Similarly we can write any *odd* integer :math:`1,3,5 \dots` as

.. math::

    o = 2k - 1

for :math:`k \in \{1,2,3 \dots\}`.  (Or as :math:`o = 2k + 1` for :math:`k \in \{0,1,2,3 \dots\}`.  If we compute the square of any even number:

.. math::

    e^2 = (2k)^2 = 4k^2 = 2(2k^2)

it is an even number.  Whereas the square of any odd number:

.. math::

    o^2 = (2k-1)^2 = 4k^2 - 4k + 1 = 2(k^2 - 2k) + 1
    
is an odd number.

+++++
Proof
+++++

The proof is by contradiction.  We assume that there does *exist* a rational number :math:`p/q` such that :math:`(p/q)^2 = 2`, and derive as a logical consequence something that is false.  This means the assumption must itself be false.

Crucially, such a rational number can always be reduced to "lowest terms" by finding and removing any common factors.  For example :math:`p` and :math:`q` cannot both be even, because if they were both even, we would factor out the :math:`2` and start with the new number :math:`p'/q'`.

Suppose

.. math::

    \frac{p}{q} = \sqrt{2}
    
     \frac{p^2}{q^2} = 2
    
    p^2 = 2q^2

Thus, :math:`p^2` must be even.  But this means, as we saw above, that :math:`p` itself must be even, because only even integers have even squares.  So we can find an integer :math:`k` such that

.. math::

    p = 2k
    
    \frac{2k}{q} = \sqrt{2}

We square again:

.. math::

    \frac{(2k)^2}{q^2} = 2

    4k^2 = 2 q^2
    
    2k^2 = q^2
    
Now we see that :math:`q^2` must be even.  But this means that :math:`q` itself must be even.

Since :math:`p` and :math:`q` are both even we have reached a contradiction.  We said that if they were both even, we could factor out the :math:`2` and have a new number :math:`p'/q'` to start with.

We have proved that the square root of two is irrational.

Here is a geometrical proof:

http://jeremykun.com/2011/08/14/the-square-root-of-2-is-irrational-geometric-proof/

