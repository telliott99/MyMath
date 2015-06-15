.. _induction:

##################
Proof by induction
##################

In the figure below we have a polygon---an irregular heptagon.  Actually, there are two polygons, there is the heptagon with :math:`n+1` sides, and also the hexagon with only :math:`n` sides that would result from cutting along the dotted line.

.. image:: /figs/polygon.png
   :scale: 50 %

What we would like to do is to find a formula for the sum of the internal angles that depends only on the number of sides or vertices.

The first part of the answer is to guess.  In the figure, you can see that by adding the extra vertex to go to the :math:`n+1`-gon, we added a triangle, or perhaps you'd rather say than in going from :math:`n+1` to :math:`n` we lost a triangle.  In either case, the difference is :math:`180^\circ`.  The difference between having :math:`n` sides and :math:`n+1` sides is to add :math:`180^\circ`.  

The second part of the argument is to suppose that :math:`n=3`, in that case we must have simply :math:`180^\circ` degrees for a triangle.  So we guess that the formula may be

.. math::

    (n-2)180^\circ = S_n

where S is the sum of the angles in an :math:`n`-gon.

We can use induction to prove that this formula is correct.

Actually, we've already done the inducing part of induction, when we guessed the formula and verified it for one or a few cases.  Now we'd like to actually prove it.  

The proof has two parts.  We must verify the formula for a base case like the triangle, which we've done.  You may wish to check that it works for the square as well, but that's not necessary.

The second part of the proof is to verify that, using the formula above, in going from :math:`n` to :math:`n+1`, we add another :math:`180^\circ`.  

.. math::

    (n-2)180^\circ + 180^\circ \stackrel{?}{=} (n-1)180^\circ

On the left-hand side, we have the sum of angles for :math:`n` sides, which we assume is correct, and then we just add :math:`180^\circ` to it.  On the right, we have substituted :math:`n+1` into the formula :math:`((n+1)-2=n-1)`.  Now we need to show that these are equivalent.

But of course this is true not just for :math:`180^\circ` but for any :math:`x`

.. math::

    (n-2)x + x 
    
    = nx - 2x + x 
        
    = nx - x 
    
    = (n-1) x

That is the inductive proof of the formula.

- We can visualize an inductive proof as a kind of chain.  We know that the "base case" is true, say for :math:`n = 3`.  We also know that if the formula works for n, it must work for n+1.

- We know it works for :math:`n = 3`;  therefore it works for :math:`n = 4`

- We know it works for :math:`n = 4`;  therefore it works for :math:`n = 5`

- We know it works for :math:`n = 5`;  therefore it works for :math:`n = 6 \cdots \ \text{and so on}`

Another famous example of induction is in the proof of the formula for the sum of the integers from :math:`1` to :math:`n`

.. math::

    1 + 2 + 3 + \dots + n = ?

We looked at this :ref:`here <sum_n^2>`.

.. math::

    \ 1 \ + \ 2 + \ 3 + \dots + \ 99 + 100
    
    100 + 99 + 98 + \dots + 2 + 1

Added together horizontally, these two series equal the sum of :math:`1 \dots 100`.  But notice that we have :math:`n` sums vertically, each of which is equal to :math:`n+1`.  We induce that

.. math::

    2S_n = n (n+1), \ \ \ \  S_n = \frac{1}{2}n(n+1)

The proof follows the inductive method.  We first check that the formula gives the correct answer for n = 1, say.  

And then we add :math:`n+1` to :math:`S_n`:

.. math::

    \frac{1}{2} n (n+1) + (n+1)

    \frac{1}{2} n (n+1) + \frac{1}{2} (2) (n+1)

    \frac{1}{2}[n(n+1) + 2(n+1)]

    \frac{1}{2}(n+2)(n+1) = S_{n+1}

Another formula that you'll see used (particularly in introducing integration) is the sum of squares of the integers 

.. math::

    \sum_{k=1}^{n} \ k^2 = 1^2 + 2^2 + 3^2 + \cdots + n^2

    \frac{n(n+1)(2n+1)}{6}

This is harder to guess, but having somehow done so, we can check the base case

.. math::

    n = 2, \ \ \ 1^2 + 2^2 = 5 = \frac{(2)(3)(5)}{6}

The other step is 

.. math::

    \frac{n(n+1)(2n+1)}{6} + (n+1)^2

    \frac{[n(n+1)(2n+1) + 6(n+1)^2]}{6}

Factor out an :math:`(n+1)`

.. math::

    \frac{(n+1) \ [n(2n+1) + 6(n+1)]}{6}

    \frac{(n+1)(2n^2 + 7n + 6)}{6}

    \frac{(n+1)(n+2)(2n+3)}{6}

    \frac{(n+1)[(n+1)+1][2(n+1)+1]}{6}

But this is just our formula, with :math:`n+1` substituted.

