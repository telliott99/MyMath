.. _series-tests:

#######################################
Infinite Series:  tests for convergence
#######################################

According to the *Calculus Lifesaver*, in order to solve problems with infinite series, the following questions should be asked in this order:

- Is the series geometric?
- Do the terms go to :math:`0` as :math:`n` goes to :math:`\infty`?
- Are there negative terms in the series?
- Are factorials involved?
- Are there tricky exponentials with :math:`n` in the base *and* exponent?
- Do the terms have a factor of exactly :math:`1/n` as well as logarithms?
- What to do if none of these tests seem to work?

We dealt with the geometric series in the :ref:`previous section <series-intro>`.

.. math::

    1 + x + x^2 + \dots
    
This series converges for :math:`|x| < 1`.

Proof:  take the nth partial sum to be :math:`S_n`.

.. math::

    S_n = 1 + x + x^2 + \dots x^n

Multiply by :math:`1-x`:

.. math::

    (1-x) S_n = 1 + x + x^2 + \dots - x - x^2 - x^3 - \dots - x^{n+1}
    
    (1-x) S_n = 1 - x^{n+1}
    
    S_n = \frac{1}{1-x} - \frac{x^{n+1}}{1-x}

If :math:`|x| < 1`, then as :math:`n \rightarrow \infty`:

.. math::

    \lim_{n \rightarrow \infty} \ \frac{x^{n+1}}{1-x} = 0
    
So 

.. math::

    S = \lim_{n \rightarrow \infty} \ S_n = \frac{1}{1-x}
    
=============
nth Term Test
=============

What is limit of the terms?

.. math::

    \lim_{n \rightarrow \infty} a_n

This limit must exist and be equal to zero, otherwise the series diverges.  However, this is not a sufficient condition for convergence.

+++++++
Example
+++++++

.. math::

    \lim_{k \rightarrow \infty} \frac{k}{2k + 1}, \ \ \ k \in \{1,2,\dots\}
    
    = \lim_{k \rightarrow \infty} \frac{1}{2 + 1/k} = \frac{1}{2} \ne 0

+++++++
Example
+++++++

.. math::

    \sum_{n=1}^{\infty} \frac{n^2 - 3n + 7}{4n^2 + 2n + 1}

The limit of the nth term is :math:`1/4`;  therefore the series diverges.

==============
Negative Terms
==============

If there are negative terms you can use the absolute convergence test or the alternating series test.  See below.

==========
Ratio Test
==========

If factorials are involved, or if the series contains exponentials but it is not geometric, try the ratio test.

.. math::

    L = \lim_{n \rightarrow \infty} |\frac{a_{n+1}}{a_n}|

If :math:`L < 1`, the series converges.  On the other hand, if :math:`L > 1` it diverges, and if :math:`L=1` the test is not informative.

Notice the absolute value signs.

+++++++
Example
+++++++

.. math::

    \sum_{n=1}^{\infty} \frac{n^{1000}}{2^n}

Here

.. math::

    \frac{a_{n+1}}{a_n} = \frac{(n+1)^{1000} \ 2^n}{n^{1000} \ 2^{n+1}}
    
    = (\frac{n+1}{n})^{1000} \ \frac{1}{2}
    
    = \frac{1}{2}

because

.. math::

    \lim_{n \rightarrow \infty} \frac{n+1}{n} = \lim_{n \rightarrow \infty} \frac{1+1/n}{1} = 1

+++++++
Example
+++++++

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k!}
    
Check

.. math::

    \lim_{k \rightarrow \infty} \frac{1/(k+1)!}{1/k!} 
    
    = \frac{k!}{(k+1)!} 
    
    = \frac{1}{k+1} < 1
    
This one is also easily checked by the comparison test (below) since

.. math::
    
    k! > k^2, \ \ \ k > 3
    
:math:`\Sigma \ 1/k^2` converges, so :math:`\Sigma \ 1/k!` also converges.

=============
Integral Test
=============

Use the integral test when the series involves both :math:`1/n` and :math:`\ln(n)`.

If the individual terms in the series :math:`a_n` are decreasing, and we know a function :math:`f(x)` which produces those terms in the series at :math:`f(n)`, and we can integrate it:

.. math::

    \sum_{n=N}^{\infty} a_n 
    
    \int_N^{\infty} f(x) \ dx

both either converge or diverge.

Here is a figure which shows the idea:

.. image:: /figs/integral-test.png
   :scale: 50 %

Note that the series in question can be either the upper sum or the lower sum.  If the integral diverges, both series diverge and if the integral converges, both series converge.  The reason is that the upper and lower sums differ by an amount that 

    is not more than the projected total on the column to the left, not more than the size of the first term we are considering.

+++++++++++++++++++++++++++++
Example (the harmonic series)
+++++++++++++++++++++++++++++

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k}

We have

.. math::

    \int_1^{\infty} \frac{1}{x} \ dx = \ln |x| \ \bigg |_1^{\infty}
    
but the upper bound has the limit

.. math::

    \lim_{k \rightarrow \infty} \ln |k| = \infty

so the integral diverges.  By the test, so does the series.

For another proof, see our look at the harmonic series in the :ref:`previous section <series-intro>`.

In general, for

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k^p}

We get convergence if :math:`p < 1`.

This leads to the following statement:

======
p-test
======

.. math::

    \sum_{n=1}^{\infty} \frac{1}{n^p} \ \ 
    \begin{cases}
        \text{converges}& \text{if } p > 1\\
        \text{diverges}& \text{if } p \le 1
    \end{cases}

+++++++
Example
+++++++

.. math::

    \int_1^{\infty} \frac{1}{n^2} \ dn = - \frac{1}{n} \ \bigg |_1^{\infty} = 0 - - 1 = 1

so :math:`\sum 1/n^2` converges.  But of course we knew that :)

+++++++
Example
+++++++

.. math::

    \sum_{n=1}^{\infty} \frac{1}{\sqrt{n}}
    
By the p-test, this diverges.  Or by the integral test

.. math::

    \int_{x=1}^{\infty} \frac{1}{\sqrt{x}} \ dx
    
    = 2 x^{1/2} \ \bigg |_{x=1}^{\infty}
    
:math:`x \rightarrow \infty` at the upper bound, it diverges.

+++++++
Example
+++++++

.. math::

    \sum_{n=2}^{\infty} \frac{1}{\ln{n}}

(:math:`n` cannot equal :math:`1`).
    
By the integral test

.. math::

    \int_{n=2}^{\infty} \frac{1}{\ln{x}} \ dx

That looks a bit difficult.  I didn't know how to do this so I searched online.  

http://monkeyraptor.johanpaul.net/2013/07/integral-calculus-ln-x-1ln-x-1xln-x-and.html

Since we're doing series, I'm going to show how it works.  We use the substitution:  :math:`u = \ln x` so :math:`du = dx/x` and we have

.. math::

    = \int \frac{1}{u} x \ du

but :math:`x = e^u` so

.. math::

    = \int \frac{e^u}{u} \ du
    
I'm not positive I know what to do with the bounds for :math:`u`:  what is :math:`\ln \infty`?  As :math:`n \rightarrow \infty`, then :math:`\ln n \rightarrow \infty` as well.  Now we tackle the integral using the *series for the exponential*:

.. math::

    = \int_0 \frac{1}{u} + 1 + \frac{u}{2!} + \frac{u^2}{3!} + \dots

    = \ln u + u + \Sigma_2^{\infty} \frac{u^n}{n \cdot n!}

    = \ln (\ln x) + \ln x + \dots

And if the bounds are right this clearly diverges because :math:`\ln x \rightarrow \infty` as :math:`x \rightarrow \infty`.

An easier way is the comparison test (below).  Since

.. math::

    \sum_{n=2}^{\infty} \frac{1}{\ln{n}}

is larger term-by term than

.. math::

    \sum_{n=2}^{\infty} \frac{1}{n}

The latter is the harmonic series, which diverges, so the first series also diverges.

+++++++
Example
+++++++

.. math::

    \sum_{n=N}^{\infty} \frac{1}{n \ln n} 

We do this:

.. math::

    \int_N^{\infty}  \frac{1}{x \ln x} \ dx
    
Substitute :math:`t = \ln x` and this becomes

.. math::

    \int_{\ln N}^{\infty}  \frac{1}{t} \ dt

which diverges. On the other hand

.. math::

    \sum_{n=N}^{\infty} \frac{1}{n (\ln n)^2} 

Also substitute :math:`t = \ln x` and this becomes

.. math::

    \int_{\ln N}^{\infty}  \frac{1}{t^2} \ dt

which *converges*.

=========
Root Test
=========

The root test says to consider

.. math::

    L = \lim_{n \rightarrow \infty} |a_n|^{1/n}

if :math:`L < 1`, then the series

.. math::

    \sum_{n=1}^{\infty} a_n 
    
converges absolutely.  If :math:`L > 1`, the series diverges, and if :math:`L = 1` then test doesn't tell you anything.

===============
Comparison test
===============

If we compare a series and a convergent series and the test series is smaller term-by-term, then it also converges.  Similarly, if a series is larger than a divergent series when compared term-by-term, it also diverges.  Any finite number of terms from the beginning of a series may be disregarded before starting the comparison.

Since

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k^2} 

converges, so does

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k^2 + 10}

And since

.. math::

    \sum_{k=0}^{\infty} \frac{1}{k}

diverges, so does

.. math::

    \sum_{k=0}^{\infty} \frac{1}{\ln|k+1|}

since for :math:`k > 2`

.. math::

    \ln |k+1| < k

so

.. math::

    \frac{1}{\ln|k+1|} > \frac{1}{k}

==============
Negative Terms
==============

If all of the terms are negative, just put a minus sign in front of each.  Compute that limit :math:`L`.  The limit of interest is :math:`-L`.

If some of the terms are negative, you can use the absolute convergence test or the alternating series test.

====================
Absolute convergence
====================

.. math::

    \text{if} \ \sum_{n=1}^{\infty} |a_n| \ \text{converges, then so does}  \ \sum_{n=1}^{\infty} a_n

==================
Alternating series
==================

This one has three steps.  I will show how it works by doing an example:

.. math::

    \sum_{n=1}^{\infty} \frac{(-1)^n}{n}

Do the terms alternate positive and negative?  Here, yes they do.

Does the series pass the nth term test when using its absolute values?  Here :math:`1/n` does tend to zero as n tends to :math:`\infty`.  So it passes.

And the third question is:  "do :math:`a_n` decrease monotonically"?  Monotonically decreasing means *always decreasing*.

Suppose we consider the partial sum :math:`S_n` for even :math:`n`.  The next two terms are

.. math::

    -\frac{1}{n+1} + \frac{1}{n+2} < 0

So

.. math::

    S_{n+2} = S_n -\frac{1}{n+1} + \frac{1}{n+2}
    
    < S_n

So this series qualifies by all three tests and is therefore convergent.  However, it is not absolutely convergent because

.. math::

    \sum_{n=1}^{\infty} |\frac{(-1)^n}{n}| = \sum_{n=1}^{\infty} |\frac{1}{n}|
    
    = 1 + \frac{1}{2} + \frac{1}{3} + \dots

is the harmonic series, which is divergent.