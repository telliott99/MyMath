.. _partial_fracs:

#################
Partial Fractions
#################

Here are some examples from Strang of the technique called partial fractions:

.. math::

    \int \frac{1}{x-2} + \frac{3}{x+2} - \frac{4}{x} \ dx

    = \ln |x-2| + 3 \ln |x+2| - 4 \ln |x|

That seems straightforward enough.  Which function would produce that sum?

.. math::

    \frac{1}{x-2} + \frac{3}{x+2} - \frac{4}{x}
    
    =\frac{(x+2)(x) + 3(x-2)(x) -4(x-2)(x+2)}{(x-2)(x+2)(x)}
    
    =\frac{x^2 + 2x + 3x^2 - 6x - 4x^2 + 16}{x^3 - 4x}
    =\frac{- 4x + 16}{x^3 - 4x}

This form is called :math:`P/Q`, and it's the type of problem we are trying to solve using partial fractions.  We start by factoring :math:`Q` (although sometimes, the factors are given).

.. math::

    Q = x^3 - 4x = x(x^2 -4) = x (x-2) (x+2)

Let's try with a different numerator to see how it works:

.. math::

    \frac{P}{Q} = \frac{3x^2 + 8x -4}{(x-2)(x+2)(x)}

    = \frac{A}{x-2} + \frac{B}{x+2} + \frac{C}{x}
    
where :math:`A`, :math:`B` and :math:`C` are constants.  These are the partial fractions that add up to :math:`P/Q`.  We need to find the values of :math:`A`, :math:`B` and :math:`C`.

Here are two methods (the first one has an extra step):

Put the right side (with :math:`A` etc.) over the common denominator :math:`Q`:

.. math::

    \frac{A}{x-2} + \frac{B}{x+2} + \frac{C}{x}

    = \frac{A(x+2)(x) + B(x-2)(x) + C(x-2)(x+2)}{(x-2)(x+2)(x)}

Now make the numerators match:

.. math::

    3x^2 + 8x -4

    = A(x+2)(x) + B(x-2)(x) + C(x-2)(x+2)

    = Ax^2 + 2Ax + Bx^2 - 2Bx + Cx^2 - 4C

We actually have three equations:

.. math::

    Ax^2 + Bx^2 + Cx^2 = 3x^2
    
    2Ax - 2Bx = 8x

    -4C = -4
    
Solve the last one to obtain :math:`C=1`.  From the first one we have:

.. math::

    A + B + C = 3

    A + B = 2
    
and then

.. math::

    A - B = 4
    
Add them together to get :math:`2A = 6, A = 31` and so :math:`B = -1`.
We obtain:

.. math::

    \frac{P}{Q} = \frac{3}{x-2} + \frac{-1}{x+2} + \frac{1}{x}

The second approach is called the "cover-up method."  Multiply by :math:`(x-2)`

.. math::

    \frac{3x^2 + 8x - 4}{(x+2)(x)} = (\frac{A}{x-2} + \frac{B}{x+2} + \frac{C}{x}) (x-2)
    
    = A +  \frac{B(x-2)}{x+2} + \frac{C(x-2)}{x}

Now evaluate the left-hand side at :math:`x=2`

.. math::

    A = \frac{3(2)^2 + 8(x) - 4}{(2+2)(2)} = \frac{12 + 16 - 4}{8} = 3

Notice that we do not need to actually write 

.. math::

    A +  \frac{B(x-2)}{x+2} + \frac{C(x-2)}{x}

Nor, in calculating :math:`B`, do we need to write

.. math::

    \frac{A(x+2)}{x-2} + B + \frac{C(x+2)}{x}

since we will pick :math:`x` to zero out those terms, instead, just substitute :math:`x=-2` into

.. math::

    \frac{3x^2 + 8x - 4}{(x-2)(x)}
    
    = \frac{3(-2)^2 + 8(-2) - 4}{(-2-2)(-2)}
    
    B = \frac{12 - 16 -4}{8} = \frac{-8}{8} = -1

===========
Same degree
===========

How about 

.. math::

    \int \frac{3x^2 + 2x + 7}{x^2 + 1} \ dx

To use the method, :math:`P` must be of a lower degree than :math:`Q`, but here they both contain multiples of :math:`x^2` (degree two).  We separate off the term of :math:`3x^2` by finding another :math:`3`:

.. math::

    \frac{3x^2 + 2x + 7}{x^2 + 1}

    = \frac{3x^2 + 3 + 2x + 4}{x^2 + 1}

    = 3 + \frac{2x + 4}{x^2 + 1}

Now we just have to solve:

.. math::

    \int 3 + \frac{2x}{x^2 + 1} + \frac{4}{x^2 + 1} \ dx

    = 3x + \ln(x^2 + 1) + 4 \tan^{-1} x + C

===============
Repeated factor
===============

.. math::

    \frac{2x+3}{(x-1)^2}

We have two factors of :math:`x-1`.  Solution:  use :math:`(x-1)^2` for one of the fractions:

.. math::

    \frac{2x+3}{(x-1)^2} = \frac{A}{x-1} + \frac{B}{(x-1)^2}

    2x + 3 = A(x-1) + B

set :math:`x=1`, then 

.. math::

    B = 2(1) + 3 = 5

and

.. math::

    2x + 3 = Ax - A + 5

:math:`A=2` solves this.

=============
More examples
=============

These few examples are from wikipedia.  We would like to simplify

.. math::

    \frac{3x+5}{(1-2x)^2}

We suppose that this fraction can be decomposed as follows
 
.. math::

    \frac{3x+5}{(1-2x)^2} = \frac{A}{(1-2x)^2} + \frac{B}{(1-2x)}

We get that by multiplying the term with :math:`B` to put everything over a common denominator:

.. math::

    \frac{A}{(1-2x)^2} + \frac{B}{(1-2x)}
    
    = \frac{A}{(1-2x)^2} + \frac{B(1-2x)}{(1-2x)^2}

Getting rid of the denominators altogether

.. math::

    3x + 5 = A + B(1-2x)
    
Now both the constant terms and the terms in :math:`x` must be equal:

.. math::

    -2Bx = 3x

    B = -\frac{3}{2}

    A + B = 5

    A = \frac{13}{2}

And so

.. math::

    \frac{3x+5}{(1-2x)^2} = \frac{13/2}{(1-2x)^2} + \frac{-3/2}{(1-2x)}

So to integrate, we would do this

.. math::

    \int \frac{3x+5}{(1-2x)^2} \ dx = \int \frac{13/2}{(1-2x)^2} \ dx + \int \frac{-3/2}{(1-2x)}  \ dx

    = \frac{13/4}{(1-2x)} +(3/4) \ln (1-2x)

=========
Example 2
=========

.. math::

    f(x) = \frac{1}{x^2 + 2x - 3} = \frac{1}{(x+3)(x-1)} = \frac{A}{x+3} + \frac{B}{x-1}

    A(x-1) + B(x+3) = 1

    Ax + Bx = 0

    A = -B

    -B + 3B = 1

    B = \frac{1}{4}

    f(x) = \frac{1}{4}( \frac{-1}{x+3} + \frac{1}{x-1} )