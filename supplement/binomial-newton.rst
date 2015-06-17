.. _binomial-newton:

#########################
Binomial Theorem:  Newton
#########################

Newton wrote the binomial expansion in this way

.. math::

    (P + PQ)^{m/n} = P^{m/n} + \frac{(m)}{(n)}P^{m/n}Q +

    \frac{(m)}{(n)}\frac{(m-n)}{(2n)}P^{m/n}Q^2 + \frac{(m)}{(n)}\frac{(m-n)}{(2n)}\frac{(m-2n)}{(3n)}P^{m/n}Q^3 + \cdots

This looks a little strange to modern eyes, but it's actually the same as the standard binomial.  The key difference is that it works for negative integers and even for a fractional power.  We can clean it up a little by factoring :math:`P^{m/n}` out of both sides

.. math::

    (P + PQ)^{m/n} = P^{m/n}(1 + Q)^{m/n}

so that

.. math::

    (1 + Q)^{m/n} = 1 + \frac{(m)}{(n)}Q + (\frac{(m)}{(n)}) \frac{(m-n)}{(2n)}Q^2 +

    \frac{(m)}{(n)}\frac{(m-n)}{(2n)}\frac{(m-2n)}{(3n)}Q^3 + \cdots

If we move :math:`n` into the numerator on the right hand side

.. math::

    (1 + Q)^{m/n} = 1 + (m/n)Q + (m/n)\frac{(m/n-1)}{2}Q^2

    + \ (m/n)\frac{(m/n-1)}{2}\frac{(m/n-2)}{3}Q^3 + \cdots

And now substitute :math:`p = m/n`

.. math::

    (1 + Q)^p = 1 + pQ + p\frac{(p-1)}{2}Q^2 + p\frac{(p-1)}{2}\frac{(p-2)}{3}Q^3 + \cdots

Suddenly it looks familiar.  Newton's formula reduces to the standard binomial, but it has the additional feature that it allows the power to be fractional (and/or negative).  Also, we don't write 

.. math::
    
    {m/n \choose k}

or the factorial version, but still subtract :math:`1,2,\cdots` from :math:`m/n` for each successive cofactor.

+++++
Usage
+++++

One way this is useful is to compute roots.  Another is to obtain a series for :math:`1/(1+x)`.

.. math::

    (1 + Q)^p = 1 + pQ + p\frac{(p-1)}{2}Q^2 + p\frac{(p-1)}{2}\frac{(p-2)}{3}Q^3 + \cdots

    (1+x)^{-1} = 1 - x + x^2 - x^3 + x^4 + \cdots

Newton checked this by multiplying:

.. math::

    1 = (1+x)(1 - x + x^2 - x^3 + x^4 + \cdots)

And if you know that the area under the curve is the logarithm, you can integrate the series for :math:`1/(1+x)` to obtain

.. math::

    \ln(1+x) = x - \frac{x^2}{2} + \frac{x^3}{3} - \frac{x^4}{4} + \cdots

The logarithms obtained by this method can be easily verified.

++++++++++
Derivation
++++++++++

AFAIK Newton did not provide a proof of his version of the binomial theorem.  I found a discussion of how he came to it here:

http://www.quadrivium.info/MathInt/Notes/NewtonBinomial.pdf

and these are my notes of this material.

.. image:: /figs/newton3.png
   :scale: 50 %

Following Wallis, Newton studied expressions for the area under various curves. These areas were apparently known, and I am not sure exactly how this was done, but I will use results obtained by integration.

It's perhaps a little confusing, but we will use :math:`x` here for two purposes.  First, the curves are :math:`f(x)=x^n` where :math:`n=0,1,2 \cdots`. Second, we seek the area under each of these curves between the endpoints :math:`1` and :math:`1+x`.  So for each :math:`n`, we will compute the integral of :math:`x^n - x^{n-1}` and evaluate that between the limits :math:`1` and :math:`1+x`.

For :math:`y = x^0`, the area under the curve is just :math:`x`.

For :math:`y = x^1`, the *additional* area is :math:`(1/2)x^2`.  

For :math:`y = x^2` we have that the additional area is

.. math::

    A = \int_1^{1+x} x^2 - x \ dx =  \frac{1}{3} x^3 - \frac{1}{2} x^2 \ \bigg |_1^{1+x}

    = \frac{1}{3} (1+x)^3 - \frac{1}{3}(1) - \frac{1}{2} (1+x)^2 - \frac{1}{2}(1)

    = \frac{1}{3} (1 + 3x + 3x^2 + x^3) - \frac{1}{3}(1) - \frac{1}{2} (1 + 2x + x^2) - \frac{1}{2}(1)

    = x + x^2 + \frac{1}{3}x^3 - x - \frac{1}{2}x^2

    = \frac{1}{2}x^2 + \frac{1}{3}x^3

Hence the total area is

.. math::

    A_{tot} = x + x^2 + \frac{1}{3}x^3

For :math:`y = x^3` we have that the additional area is

.. math::

    A = \int_1^{1+x} x^3 - x^2 \ dx =  \frac{1}{4} x^4 - \frac{1}{3} x^3 \ \bigg |_1^{1+x}

    = \frac{1}{4} (1+x)^4 - \frac{1}{4}(1) - \frac{1}{3} (1+x)^3  - \frac{1}{3}(1)

    = \frac{1}{4}(4x + 6x^2 + 4x^3 + x^4) - \frac{1}{3} (3x + 3x^2 + x^3)

    = \frac{1}{2}x^2 + \frac{2}{3}x^3 + \frac{1}{4}x^4

Hence the total area is

.. math::

    A_{tot} = x + \frac{3}{2}x^2 + \frac{3}{3}x^3 + \frac{1}{4}x^4

If we carried out this exercise for the fourth and fifth powers we would find

.. math::

    A_{tot} = x + \frac{4}{2}x^2 + \frac{6}{3}x^3 + \frac{6}{4}x^4 + \frac{1}{5}x^5

    A_{tot} = x + \frac{5}{2}x^2 + \frac{10}{3}x^3 + \frac{10}{4}x^4 + \frac{5}{5}x^5 + \frac{1}{6}x^6

If we look carefully at what we've obtained, we see that there is a sum of terms like :math:`x^p/p` times a cofactor which goes like Pascal's triangle or a standard binomial expansion (and indeed, that's where it came from).  Newton organized the cofactors into a table.

.. math::

    \begin{matrix}
    \text{p}  \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6 \\
    x^7/7
    \end{matrix} \ \ \ \
    \begin{matrix}
    0 & 1 & 2 & 3 & 4 & 5  \\
    1 & 1 & 1 & 1 & 1 & 1  \\
    0 & 1 & 2 & 3 & 4 & 5 \\
    0 & 0 & 1 & 3 & 6 & 10 \\
    0 & 0 & 0 & 1 & 4 & 10 \\
    0 & 0 & 0 & 0 & 1 & 5 \\
    0 & 0 & 0 & 0 & 0 & 1 \\
    0 & 0 & 0 & 0 & 0 & 0
    \end{matrix}

That is, we have for :math:`x^2` that the area is

.. math::

    (1)x + (2)\frac{1}{2}x^2 + (1)\frac{1}{3}x^3 = x + x^2 + \frac{1}{3}x^3

Newton noticed the pattern which is so clear in Pascal's triangle, that the coefficients can be generated by addition.  For example, the :math:`6` in the column for :math:`n=4` is generated by adding together the two entries of :math:`3` to its immediate left and upper-left.  Thus, having the first row (all :math:`1`), and the column under :math:`n=0`, one can generate the rest of the table mechanically.

Now, Newton says, what happens if we add an additional column for :math:`n=-1`, and it follows the rule that the entry in the first row must be :math:`1`?

.. math::

    \begin{matrix}
    \text{p}  \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6 \\
    x^7/7
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & 0 & 1 & 2 & 3 & 4 & 5  \\
    \ \ 1 & 1 & 1 & 1 & 1 & 1 & 1  \\
    \ \ . & 0 & 1 & 2 & 3 & 4 & 5 \\
    \ \ . & 0 & 0 & 1 & 3 & 6 & 10 \\
    \ \ . & 0 & 0 & 0 & 1 & 4 & 10 \\
    \ \ . & 0 & 0 & 0 & 0 & 1 & 5 \\
    \ \ . & 0 & 0 & 0 & 0 & 0 & 1 \\
    \ \ . & 0 & 0 & 0 & 0 & 0 & 0
    \end{matrix}

How do we fill  in the missing entries?  By using the addition rule!  The first missing value must be a :math:`-1`, so that it plus the :math:`1` above add together to give the :math:`0` to its right.

.. math::

    \begin{matrix}
    \text{p}  \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6 \\
    x^7/7
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & 0 & 1 & 2 & 3 & 4 & 5  \\
    \ \ 1 & 1 & 1 & 1 & 1 & 1 & 1  \\
    -1 & 0 & 1 & 2 & 3 & 4 & 5 \\
    \ \ . & 0 & 0 & 1 & 3 & 6 & 10 \\
    \ \ . & 0 & 0 & 0 & 1 & 4 & 10 \\
    \ \ . & 0 & 0 & 0 & 0 & 1 & 5 \\
    \ \ . & 0 & 0 & 0 & 0 & 0 & 1 \\
    \ \ . & 0 & 0 & 0 & 0 & 0 & 0
    \end{matrix}

He filled out the rest of the column for :math:`n=-1` using this idea.

.. math::
  
    \begin{matrix}
    \text{p}  \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6 \\
    x^7/7
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & 0 & 1 & 2 & 3 & 4 & 5  \\
    \ \ 1 & 1 & 1 & 1 & 1 & 1 & 1  \\
    -1 & 0 & 1 & 2 & 3 & 4 & 5 \\
    \ \ 1 & 0 & 0 & 1 & 3 & 6 & 10 \\
    -1 & 0 & 0 & 0 & 1 & 4 & 10 \\
    \ \ 1 & 0 & 0 & 0 & 0 & 1 & 5 \\
    -1 & 0 & 0 & 0 & 0 & 0 & 1 \\
    \ \ 1 & 0 & 0 & 0 & 0 & 0 & 0
    \end{matrix}


This gives the series for :math:`1/(1+x)` that we have above.  

.. math::

    \frac{1}{1+x} = 1 - x + x^2 - x^3 + x^4 + \cdots

One can check that it's correct by multiplying out.

.. math::

    1 = 1 - x + x - x^2 + x^2 - x^3 + x^3 - x^4 + x^4 + \cdots  = 1

Using this idea, one can fill in the table for the negative integers.  

.. math::
  
    \begin{matrix}
    \text{p}  \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6 \\
    x^7/7
    \end{matrix} \ \ \ \
    \begin{matrix}
    -3 & -2 & -1 & 0 & 1 & 2 & 3 & 4 & 5  \\
     \ \ 1 & \ \ 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 & 1  \\
    -3 & -2 & -1 & 0 & 1 & 2 & 3 & 4 & 5 \\
     \ \ 6 & \ \ 3 & \ \ 1 & 0 & 0 & 1 & 3 & 6 & 10 \\
    -10 & -4 & -1 & 0 & 0 & 0 & 1 & 4 & 10 \\
     \ \ 15 & \ \ 5 & \ \ 1 & 0 & 0 & 0 & 0 & 1 & 5 \\
    -21 & -6 & -1 & 0 & 0 & 0 & 0 & 0 & 1 \\
     \ \ 28 & \ \ 7 & \ \ 1 & 0 & 0 & 0 & 0 & 0 & 0
    \end{matrix}


For :math:`1/(1+x)^2` we will have  

.. math::

    \frac{1}{(1+x)^2} = 1 - 2x + 3x^2 - 4x^3 + 5x^4 + \cdots

You can check that :ref:`here <series-intro>`, or just multiply out by :math:`(1+x)`.

.. math::

    = 1 - 2x + 3x^2 - 4x^3 + 5x^4 + \dots
    
    \ \ \ + x - 2x^2 + 3x^3 - 4x^4 + \dots
    
    = 1 - x + x^2 - x^3 + x^4 + \dots
    
    = \frac{1}{1+x}


What about fractional powers?

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5 \\
    x^6/6
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3   \\
    \ \ 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ . & 0 & . & 1 & . & 2 & . & 3 \\
    \ \ 1 & \ \ . & 0 & . & 0 & . & 1 & . & 3 \\
    -1 &  \ \ .  & 0 & . & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 & . & 0 & . & 0 & . & 0 \\
    -1 &   \ \  . & 0 & . & 0 & . & 0 & . & 0 \\
    \end{matrix}

After a lot of work, Newton comes to two simple ideas.  First, the addition rule remains in place, for entries that are separated by a whole unit.  (The missing entries in the table above depend not on the entries to the immediate left, but one more column over.  Given one of these missing entries, the entire row can be filled in.  Let's try

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \ \ \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3  \\
    \ \ 1 & \ \ 1 & 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ -1/2 \ \ & 0 & \ \ 1/2 & 1 & 3/2 & 2 & 5/2 & 3 \\
    \ \ 1 & \ \ . & 0 &  . & 0 & . & 1 & . & 3 \\
    -1 &  \ \ .  & 0 & . & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 & . & 0 & . & 0 & . & 0 \\
    \end{matrix}

I won't fill in the rest of the entries just yet, except the column for the :math:`1/2` power

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \ \ \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3  \\
    \ \ 1 & \ \ 1 & 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ -1/2 \ \ & 0 & \ \ 1/2 & 1 & 3/2 & 2 & 5/2 & 3 \\
    \ \ 1 & \ \ . & 0 &  -1/4 & 0 & . & 1 & . & 3 \\
    -1 &  \ \ .  & 0 & \ \ 3/16 & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 & -15/96 & 0 & . & 0 & . & 0 \\
    \end{matrix}

Again, this is all according to 

http://www.quadrivium.info/MathInt/Notes/NewtonBinomial.pdf

The pattern is

.. math::

    \begin{matrix}
    a & a & a & a & a \\
    b & a+b & 2a+b & 3a+b & 4a+b \\
    c & b+c & a+2b+c & 3a+3b+c & 6a+4b+c \\
    d & c+d & b+2c+d & a+3b+3c+d & 4a+6b+4c+d
    \end{matrix}

and so on.  What Newton does at this point is to substitute new variables.  With this "decoupling" the rows become *independent*.  So we replace the table above with this:

.. math::

    \begin{matrix}
    a & a & a & a & a \\
    b & c+b & 2c+b & 3c+b & 4c+b \\
    d & e+d & f+2e+d & 3f+3e+d & 6f+4e+d \\
    g & h+g & i+2g+h & k+3i+3h+g & 4k+6i+4h+g
    \end{matrix}

To solve the second row, one needs two entries.  Obtain :math:`c` by the difference between them, then solve for :math:`b`.  For the third row, we need three entries.

But we have them!

The second row is (starting with the usual first column headed by :math:`0`, rather than the negative exponents from above):

.. math::

    \begin{matrix}
    0 & ? & 1 & ? & 2 \\
    \end{matrix}

Referring to the table, we have these equations:

.. math::

    b = 0
    
    2c + b = 1
    
    4c + b = 2
    
So

.. math::

    c = \frac{1}{2}

and the row is then

.. math::

    \begin{matrix}
    0 & \frac{1}{2} & 1 & \frac{3}{2} & 2 \\
    \end{matrix}

compare with:

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \ \ \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3  \\
    \ \ 1 & \ \ 1 & 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ -1/2 \ \ & 0 & \ \ 1/2 & 1 & 3/2 & 2 & 5/2 & 3 \\
    \ \ 1 & \ \ . & 0 & \ \ . & 0 & . & 1 & . & 3 \\
    -1 &  \ \ .  & 0 &  \ \ . & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 &  \ \ .  & 0 & . & 0 & . & 0 \\
    \end{matrix}

Given any single fractional entry in a row, we can fill in the rest.

Let's finish up with the third row.  We have:

.. math::

    \begin{matrix}
    0 & ? & 0 & ? & 1 \\
    \end{matrix}

From the table:

.. math::

    \begin{matrix}
    a & a & a & a & a \\
    b & c+b & 2c+b & 3c+b & 4c+b \\
    d & e+d & f+2e+d & 3f+3e+d & 6f+4e+d \\
    g & h+g & i+2g+h & k+3i+3h+g & 4k+6i+4h+g
    \end{matrix}

We have these equations:

.. math::

    d = 0
    
    f + 2e + d = 0
        
    6f + 4e + d = 1
    
So

.. math::

    f + 2e = 0
    
    f = -2e

    -12e + 4e = 1
    
    e = -\frac{1}{8}
    
    f = \frac{1}{4}
    
The entry in row three for :math:`1/2` is:  :math:`e+d = -1/8` and the entry in the same row for :math:`3/2` is :math:`3f + 3e + d = 3/8`.

compare with:

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \ \ \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3  \\
    \ \ 1 & \ \ 1 & 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ -1/2 \ \ & 0 & \ \ 1/2 & 1 & 3/2 & 2 & 5/2 & 3 \\
    \ \ 1 & \ \ . & 0 &  -1/8 & 0 & 3/8 & 1 & . & 3 \\
    -1 &  \ \ .  & 0 & . & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 & . & 0 & . & 0 & . & 0 \\
    \end{matrix}

Having any single entry we can fill out the row:

.. math::

    \begin{matrix}
    \text{p} \\
    x/1  \\
    x^2/2 \\
    x^3/3 \\
    x^4/4 \\
    x^5/5
    \end{matrix} \ \ \ \
    \begin{matrix}
    -1 & -\frac{1}{2} & 0& \ \ \frac{1}{2} & 1& \frac{3}{2}  & 2 & \frac{5}{2}  & 3  \\
    \ \ 1 & \ \ 1 & 1 & \ \ 1 & 1 & 1 & 1 & 1 & 1 \\
    -1 & \ \ -1/2 \ \ & 0 & \ \ 1/2 & 1 & 3/2 & 2 & 5/2 & 3 \\
    \ \ 1 & \ \ 5/8 & 0 &  -1/8 & 0 & 3/8 & 1 & 15/8 & 3 \\
    -1 &  \ \ .  & 0 & . & 0 & . & 0 & . & 1 \\
    \ \ 1 &  \ \ . & 0 & . & 0 & . & 0 & . & 0 \\
    \end{matrix}

Here is the last table from the article.

.. image:: /figs/newton_table.png
   :scale: 50 %

With these in hand, Newton puzzled over the pattern, and came up with the formula we saw at the beginning of this chapter.
