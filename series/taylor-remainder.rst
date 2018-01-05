.. _taylor-remainder:

#########################
Taylor Series:  Remainder
#########################

Taylor series are used in constructing a polynomial approximation to some difficult function, to allow estimation of the value of the function at :math:`x=a` or in some interval near :math:`a`.

The general approach for :math:`x \approx a` is the Taylor series.  Here is the formula:

.. math::

    f(x) = \sum_{n=0}^{n=\infty} \frac{f^n(a)}{n!} (x-a)^n

The most important approximation is for :math:`a = 0` and that is called the Maclaurin series.

.. math::

    f(x) = \sum_{n=0}^{n=\infty} \frac{f^n(0)}{n!} (x)^n

=====
Error
=====

A Taylor series is an infinite series, but in practice we will choose a limited number of terms to sum up, and would like to know the possible error in doing so.

If we write out the series to the (n+1)th term:

.. math::

    f(x) = f(a) + f'(a) (x-a) + f^2(a) \frac{(x-a)^2}{2} + \dots + f^{n-1}(a) \frac{(x-a)^{n-1}}{(n-1)!} + + f^n(a) \frac{(x-a)^n}{n!}

Because we start with the zeroth derivative of :math:`f(x)`, the function itself, the series ending with :math:`f^n(x)` has :math:`n+1` terms.  So, for working problems, be careful about counting.

Kline derives a formula (I don't exactly understand the derivation yet):  it is exactly equal to the Taylor series but contains a finite number of terms.   That expression is:

.. math::

    f(x) = f(a) + f'(a) (x-a) + f^2(a) \frac{(x-a)^2}{2} + \dots + + f^n(a) \frac{(x-a)^n}{n!} + + f^{n+1}(c) \frac{(x-a)^{n+1}}{(n+1)!}

**where c lies between x and a**.  We don't know what :math:`c` is, but we know there is at least one such value, because of the "generalized" mean value theorem.  For :math:`n=1` we have:

.. math::

    f(x) = f(a) + f'(c) (x-a)

Does this look familiar?  It is the mean value theorem (MVT).  It says that if we take the *average* slope over an interval

.. math::

    \frac{f(b) - f(a)}{b-a} = f'(c)

There is *at least one* point :math:`c` in the interval :math:`[a,b]` where the slope matches.

.. image:: /figs/mvt.png
       :scale: 25%

=========
Remainder
=========

We say that

.. math::

    R_n(x) = f(x) - T_n(x)

The "remainder" :math:`R` is the difference between the true value of the function and the approximation we make by truncating the Taylor series.  We are interested in estimating :math:`R`.  The **remainder theorem** says that (if :math:`f` is :math:`n+1` times differentiable, and :math:`R` is so defined) then:

.. math::

    R_n(x) = \frac{f^{n+1}(c)}{(n+1)!} (x-a)^{n+1}

for some :math:`c` beween :math:`a` and :math:`x`.

This is basically what Kline said, see above.

To use the theorem to estimate ("bound") the error in an approximation:

First, find an upper-bound, :math:`M`, on the absolute value of the :math:`n +` 1st derivative of :math:`f` between :math:`a` (the center) and :math:`x` (where you want to bound the error).
    
The error :math:`|R_n(x)|` is *at most*:

.. math::

    |R_n(x)| \le M \ \frac{1}{(n+1)!} \ |x-a|^{n+1}

+++++++
Example
+++++++

Suppose that

.. math::

    f(x) = \sqrt[3]{x}

We are asked:  what is the maximum possible error if the Taylor polynomial of degree :math:`2` for the function centered at :math:`a = 8` is used to approximate :math:`f(x)` in the interval :math:`|x-a| \le 1`?

The Taylor polynomial of degree :math:`2` extends to the term with :math:`(x-a)^2`, so the remainder has a term containing :math:`3`.

Let's take some derivatives:

.. math::

    f'(x) = \frac{1}{3} x^{-2/3}
    
    f''(x) = -\frac{2}{9} x^{-5/3}
    
    f'''(x) = \frac{10}{27} x^{-8/3}

Now, we need to fix an upper bound for the value of this last derivative over the interval :math:`|x-a| \le 1`, (since :math:`a = 8` that interval is:  :math:`[7,9]`).

So the question is:  how large can the following expression be?

.. math::

    \frac{10}{27} c^{-8/3}

given that :math:`c` is in the interval given above?  Since :math:`c` has a negative exponent larger than one, the biggest value is for the smallest :math:`c` in the interval, that is, :math:`c=7`.  So then :math:`M` is the absolute value of this (since the number is :math:`> 0`, we get rid of the absolute value signs):

.. math::

    M = \frac{10}{27} \frac{1}{7^{8/3}}

    |R_n(x)| \le M \ \frac{1}{(n+1)!} \ |x-a|^{n+1}
    
    |R_n(x)| \le \frac{10}{27} \frac{1}{7^{8/3}} \ \frac{1}{3!}  \ |x-8|^{n+1}

Since :math:`0 \le |x-8| \le 1`, the largest value for the last part is just :math:`1` and we have that

.. math::

    |R_n(x)| \le \frac{10}{27} \ \frac{1}{7^{8/3}} \ \frac{1}{3!}

+++++++
Example
+++++++

What is the maximum possible error if the Taylor polynomial of degree 4 for the function :math:`f(x) = e^x` centered at :math:`0` is used to approximate :math:`e^{0.2}`?

The fifth derivative :math:`f^5` of :math:`e^x` is just equal to :math:`e^x`.

We need to find an upper-bound, :math:`M`, on the absolute value of the :math:`n +` 1st derivative of :math:`f` between :math:`a` (the center) and :math:`x` (where you want to bound the error).  So the interval is :math:`[-0.2,0.2]` and the value of the derivative is largest at the right-hand bound and we have:

.. math::

    M = e^{0.2}

and 

.. math::

    |R_n(x)| \le M \ \frac{1}{(n+1)!} \ |x-a|^{n+1}

    |R_4(0.2)| \le e^{0.2} \ \frac{1}{5!} \ |0.2|^{5}
    
Now

.. math::

    e^{0.2} \approx 1.22
    
    \frac{1}{5!} \approx 0.008333
    
    0.2^{5} = 0.00032
    
The result is :math:`\approx 0.00000326`.

+++++++
Example
+++++++

What degree Taylor polynomial for :math:`\sin x` (centered at :math:`0`) must you use in order to approximate :math:`\sin 1` to within :math:`0.001` accuracy?

We have a center :math:`a=0` and :math:`x=1` where we want to bound the error, so the interval is :math:`[-1,1]`.  We know that all the derivatives of :math:`\sin x` are bounded between :math:`-1` and :math:`1`, so the absolute value is less than :math:`1`.

.. math::

    0 \le M \le 1

This simplifies:

.. math::

    |R_n(x)| \le M \ \frac{1}{(n+1)!} \ |x-a|^{n+1}

    \le \frac{1}{(n+1)!} \ |x-a|^{n+1}

    \le \frac{1}{(n+1)!}

(because :math:`a = 0` and :math:`x = 1`).

If we choose :math:`n=5`, then :math:`1/6! = 1/720 \approx 0.001388` which is a bit too large.  Thus, we need :math:`n=6` with :math:`1/7! \approx 0.000198`.

+++++++
Example
+++++++

Find :math:`\sqrt{e}` to within an error of :math:`10^{-4}`.

Take :math:`f(x)` to be :math:`e^x` and :math:`x=1/2`.  Take the series around :math:`c=0` (Maclaurin series).  The derivatives of :math:`e^x` are all just :math:`e^x`.

So what is the upper bound for

.. math::

    M_n = e^x

in the interval :math:`0 \le \mu \le 1/2`?  It is obviously :math:`e^{1/2}`.  In the book (Varberg), they let the interval be :math:`[0,1]` with upper bound :math:`e^1`, and then take :math:`M_n = 3` because it's "easy to deal with".

So now for each value of :math:`n`, with :math:`M_n = 3` we calculate the value of

.. math::

    E_n < M_n \frac{(1/2)^n}{n!}

    E_1 < 3 \frac{1}{2} = \frac{3}{2}
    
    E_2 < 3 \frac{(1/2)^2}{2!} = 

    E_3 < 3 \frac{(1/2)^3}{3!} = 

    \dots

Sparing all the details, :math:`E_6` is the first error term within the prescribed bounds

.. math::

    E_6 < 3 \frac{(1/2)^6}{6!} = 3 \frac{1}{64} \frac{1}{720} = \frac{3}{46080} = 6.51 \times 10^{-5}

so we need the series out to :math:`n=5`

.. math::

    \sqrt{e} = \sum_{n=0}^5 \frac{(1/2)^n}{n!}
    
    = 1 + 1/2 + 1/8 + 1/48 + 1/384 + 1/3840
    
    = 1.6487
    
    (1.6487)^2 = 2.7182
    
