.. _limits-basic:

######
Limits
######

As Varberg says:

    First, we follow a long tradition in using the Greek letters :math:`\epsilon` (epsilon) and :math:`\delta` (delta) to stand for arbitrary positive numbers.  Think of :math:`\epsilon` and :math:`\delta` as small positive numbers.

We propose to show (if we can), that as :math:`x` gets very close to some number :math:`c`, the value of a function :math:`f(x)` gets very close to the limit :math:`L`.

One strange thing about this process is that we do not require that the function :math:`f(x)` actually makes sense at :math:`c`---:math:`f(c)` need not exist at that point.

As an example:

.. math::

    \frac{1-x}{(1-x)^2} = \frac{(1-x)}{(1-x)(1+x)}
    
    = \frac{1}{1+x}

The proscription on division by zero means the function on the first line isn't defined at :math:`x=1`.  On the other hand, the second function is.  Other than that, they share all the same values.

To go back to the limit part:  think of it as a game involving Emily and David.  Emily is allowed to specify how close to the proposed limit :math:`L` the value of the function :math:`f(x)` has to be.  Emily sets the *standard*, and David must try to find a way to reach it.

In geek speak:

.. math::

    L - \epsilon < f(x) < L + \epsilon
    
    |f(x) - L| < \epsilon

The game part is that Emily gets to choose :math:`\epsilon` to be really, really small.

David wins *if* he can cook up some :math:`\delta` to specify an interval around :math:`c`, but not actually including it (an open interval with a hole in it)

.. math::

    0 < | x - c | < \delta

(note that the difference must be :math:`> 0`), and then if

.. math::

    |f(x) - L| < \epsilon

for *all* :math:`x` in this interval, we can say that the limit of the function :math:`f(x)` at :math:`x=c` is actually :math:`L`.

Here is a figure I found on the web:

.. image:: /figs/limit-e-d.png
   :scale: 50 %

===========
Sine of 1/x
===========

The classic example of a limit that does not exist is:

.. math::

    \lim_{x \rightarrow \infty} \ \sin x

Here is a proof I found on the web:

https://www.math.ucdavis.edu/~osserman/classes/21A-F12/exam1-practice-sols.pdf

.. image:: /figs/limit1.png
   :scale: 50 %

We can also rewrite this using :math:`u = 1/x`.  Then, as :math:`x \rightarrow \infty`, :math:`u \rightarrow 0` so this is the same problem:

.. math::

    \lim_{u \rightarrow 0} \ \sin \frac{1}{u}

and it has the same answer.  Here is a picture:

.. image:: /figs/limit3.png
   :scale: 50 %

On the other hand, what about

.. math::

    \lim_{x \rightarrow 0} \ x \sin \frac{1}{x}

It turns out that this limit *does* exist.  Here is a proof:

.. image:: /figs/limit2.png
   :scale: 50 %

And here is a picture:

.. image:: /figs/limit4.png
   :scale: 50 %

In this example, it doesn't matter what's inside the sine function since

.. math::

    -1 \le \sin t \le 1

    |\sin t| \le 1

and since

.. math::

    \lim_{t \rightarrow 0} \ t = 0

the product of limits:

.. math::

    \lim_{t \rightarrow 0} \ t \sin t = 0
    
because we have the limit zero times something which is finite, so the product with zero is zero.

++++++++
Examples
++++++++

