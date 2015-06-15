.. _exp-binomial:

##########################
Using the binomial theorem
##########################

Evaluating

.. math::

    \lim_{x \rightarrow \infty} e = (1 + \frac{1}{x})^{x}

If we use the standard binomial expansion

.. math::

    \frac{1}{0!}a^n + \frac{n}{1!}a^{n-1}b^1 + \frac{n(n-1)}{2!}a^{n-2}b^2 + \frac{n(n-1)(n-2)}{3!}a^{n-3}b^3\ + \cdots

with :math:`a = 1`

.. math::

    \frac{1}{0!} + \frac{n}{1!}b^1 + \frac{n(n-1)}{2!}b^2 + \frac{n(n-1)(n-2)}{3!}b^3\ + \cdots

plug in for :math:`b = 1/n`

.. math::

    \frac{1}{0!}({\frac{1}{n}})^0 + + \frac{n}{1!}({\frac{1}{n}})^1 + \frac{n(n-1)}{2!}({\frac{1}{n}})^2 + \frac{n(n-1)(n-2)}{3!}({\frac{1}{n}})^3 + \cdots

Now, in the limit as :math:`x \rightarrow \infty`, :math:`n` and :math:`n-1` are nearly equal, and so are :math:`n` and :math:`n-2`, and all the terms :math:`n`, :math:`(n-1)`, :math:`(n-2)1 find just the right number of :math:`n`'s in the denominator to cancel and we get

.. math::

    \frac{1}{0!} + \frac{1}{1!} + \frac{1}{2!} + \frac{1}{3!} + \cdots
    
which is one of the definitions we gave above for :math:`e`, and evaluated as :math:`e = 2.718`.  

So :math:`e` is just a number.  We can define the exponential function, which means we raise :math:`e` to the power :math:`x`, that is :math:`f(x) = e^x`.  We have

.. math::

    e = \lim_{n \to \infty} (1 + \frac{1}{n})^{n}

We want 

.. math::

    e^x = \lim_{n \to \infty} (1 + \frac{1}{n})^{nx}

It turns out this is exactly the same as

.. math::

    e^x = \lim_{n \to \infty} (1 + \frac{x}{n})^{n}

It seems counterintuitive.  But the result follows from

.. math::

    (1+b)^{mn} = (1+mb)^n

To confirm this, look at the binomial expansion for these two expressions.  Remember that the terms :math:`n(n-1)(n-2)(n-3)` etc. come from this formula

.. math::

    \frac{n!}{(n-k)!k!}

so for example, with :math:`k=3` we have

.. math::

    n! = n \times (n-1) \times (n-2) \times (n-3)!

    \frac{n!}{(n-k)!k!} = \frac{n(n-1)(n-2)(n-3)!}{(n-3)!\ 3!}
    
    = \frac{n(n-1)(n-2)}{3!}

Thus, in the first one

.. math::

    e^x = \lim_{n \to \infty} (1 + \frac{1}{n})^{nx}

With :math:`nx` as the exponent, the factorial part is

.. math::

    \frac{(nx)!}{((nx)-k)!\ k!}

so for example the :math:`k=3` term is

.. math::

    \frac{nx \times (nx-1) \times (nx-2)}{3!}

we get a power of :math:`nx` coming in for each term in the numerator

.. math::

    \frac{1}{0!}({\frac{1}{n}})^0 + + \frac{nx}{1!}({\frac{1}{n}})^1 + \frac{nx(nx-1)}{2!}({\frac{1}{n}})^2 + \frac{nx(nx-1)(nx-2)}{3!}({\frac{1}{n}})^3 + \cdots

The subtracted value of :math:`k` is negligible in the limit, and the :math:`n`'s cancel as before but the :math:`x`'s do not, so that gives finally

.. math::

    e^x = \frac{x^0}{0!} + \frac{x^1}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \dots

Now, the second version is

.. math::

    \lim_{n \to \infty} (1 + \frac{x}{n})^{n}

    \frac{1}{0!}(\frac{x}{n})^0 + + \frac{n}{1!}({\frac{x}{n}})^1 + \frac{n(n-1)}{3!}({\frac{x}{n}})^2 + \frac{n(n-1)(n-2)}{3!}({\frac{x}{n}})^3 + \cdots

The :math:`n`'s cancel as before and we have

.. math::

    e^x = \frac{x^0}{0!} + \frac{x^1}{1!} + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots

    = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots

Note:  this assumes that the binomial applies to fractional exponents, which is true but a bit complicated to show.

Also note that a very useful approximation for small :math:`x` is

.. math::

    e^x \approx 1 + x

If you need more precision, you can add another term:

.. math::

    e^x \approx 1 + x + \frac{x^2}{2!}