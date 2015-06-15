.. _exp-basics:

#########################
Exponential and Logarithm
#########################

The logarithm and exponential functions are inverses.  If we have that

.. math::

    y = b^x

for some :math:`b > 0, b \ne 1`, then we say that

.. math::

    x = \log_b \ y
    
Putting them together

.. math::

    y = b^{\ \log_b y}

The usual bases are :math:`10` (common logarithm, :math:`\log_{10}`, or just :math:`\log`), :math:`e` (natural logarithm or :math:`\ln`), and :math:`2` (binary logarithm or :math:`\log_2`).

The rules for exponents are simple, if :math:`p` and :math:`q` are two numbers and we know the logarithms :math:`u` and :math:`v` of :math:`p` and :math:`q` to base :math:`b`

.. math::

    p = b^{u}; \ \ \ q = b^{v}

then their product can be found as:

.. math::

    pq = b^{u + v}

provided we can actually compute :math:`b^{u+v}`.  In the old days there were tables of logarithms, so you just looked up the answer in the table.

The second rule is that:

.. math::

    (b^u)^v = b^{uv}

And in terms of logarithms we write

.. math::

    \log_b (b^u)^v = \log b^{uv} = v \log_b (b^u)

For example 

.. math::

    2^2 = 2 \times 2 = 4

    2^3 = 2 \times 2 \times 2 = 8

    4 \times 8 = 2^2 \times 2^3 = 2^{2 + 3} = 2^5

    = 2 \times  2 \times 2 \times 2 \times 2 = 32

and

.. math::

    \log_2 (2^2)^3 = 3 \log_2 4 = 6

    (2^2)^3 = 4^3 = 64 = 2^6 = 2^{2 \times 3}

Here is a plot of :math:`\log_{10}(x)` and :math:`\ln x`:

.. image:: /figs/log1.png
   :scale: 50 %

The first function reaches the value :math:`1` when :math:`x=10` and the second reaches the value :math:`1` when :math:`x=e = 2.71828`.  Both have the value :math:`0` at :math:`x=1` because :math:`b^0 = 1` for any base, so the logarithm to any base of :math:`1` is equal to :math:`0`.

Since

.. math::

    x \ \frac{1}{x} = 1

    \log ( x \cdot \frac{1}{x} ) = \log 1 = 0

so

.. math::

    \log x + \log \frac{1}{x} = 0

    - \log x = \log \frac{1}{x}

It turns out that if we take the logarithm of :math:`x` (where :math:`x` is any number :math:`> 1`) to two *different* bases, the ratio of the logarithms is a constant, independent of the value of :math:`x`.  This is illustrated by the change of bases formula.

.. math::

    \log_a b \ \log_b n = \log_a n

To remember this, I think of the :math:`b`'s on the left-hand side "cancelling", although they don't really.  Rearranging:

.. math::

    \log_b n = \frac{\log_a n}{\log_a b}

To derive the formula, start with:

.. math::

    y = b^x

    x = \log_b y

Take the logarithm to the base :math:`a`:

.. math::

    \log_a y = \log_a (b^x)

Use the second rule

.. math::

    \log_a y = x \log_a b

Substitute for :math:`x`

.. math::

    \log_a y = \log_b y \log_a b
        
which is what we had, expressed in terms of :math:`y` rather than :math:`x`.  If you prefer:

.. math::

    \log_a x = \log_a b \log_b x

Rearranging:

.. math::

    \log_b y = \frac{\log_a y}{\log_a b}

To check this:

.. math::

    \log_b x = k \log_a x

the logarithms to different bases are connected by some constant :math:`k`, and we substitute for :math:`k` the inverse of the log to the *same* base as we have in the numerator:

.. math::

    \log_b x = \frac{\log_a x}{\log_a b}

One other thing we can do is to set :math:`x=a` in the above formula.  We start from

.. math::

    \log_b x = \frac{\log_a x}{\log_a b}

then with :math:`x=a`

.. math::

    \log_b a = \frac{\log_a a}{\log_a b}

but :math:`\log_a a = 1` so

.. math::

    \log_b a = \frac{1}{\log_a b}

And that makes perfect sense.  If we multiply by some factor :math:`c` to convert from the logarithm in base :math:`a` to base :math:`b`, we must multiply by the inverse of the same factor to convert back again.

For the figure above of the common log (base 10) and the natural logarithm, :math:`\ln 10 = 2.303`, and that looks about right, when :math:`x=10` the first function is :math:`1.0` and the second one is about :math:`2.3`.

The logarithm and the exponential are inverse functions, we can see that if we plot them together:

.. image:: /figs/log2.png
   :scale: 50 %

The upper curve is :math:`y = e^x` and the lower one is :math:`y = \ln x`.

As inverse functions, they are symmetric about the line :math:`y=x`.  Also, if we consider an :math:`x` value, for example :math:`x=1`, then the slope of the curve :math:`y=e^x` at :math:`x=1` (at the point :math:`(1,e)`) is the inverse of the slope of the curve :math:`y=log(x)` when :math:`x=e` (at the point :math:`(e,1)`).

====================
Fractional Exponents
====================

The introduction above dealt mainly with integer exponents, but of course you know that the practical use of logarithms depends on fractional values.  The simplest way to see how this works is to consider the square root.

.. math::

    \sqrt{2} \times \sqrt{2} = 2

If we think about what the exponent :math:`u` to the base :math:`2` would be such that

.. math::

    2^u = \sqrt{2}

We observe that by the rules for exponents

.. math::

    \sqrt{2} \times \sqrt{2} = 2^u \times 2^u = 2^{u+u} = 2^1

That is

.. math::

    u + u = 1

so :math:`u = 1/2`.  By the same logic the :math:`n^{\text{th}}` root of :math:`b` is :math:`b^{1/n}`.  And of course 

.. math::

    (b^2)^{1/2} = b^{2 \times 1/2} = b^1

Feynman has a nice description of how logarithms were calculated (see Lectures, volume 1, Chapter 22, Algebra;

http://www.feynmanlectures.caltech.edu/I_22.html

The basic idea is to take repeated square roots of the base (:math:`10`), and then combine those to form the required value.