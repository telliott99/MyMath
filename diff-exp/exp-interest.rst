.. _exp-interest:

######################
Principal and interest
######################

Suppose I put :math:`100` dollars in the bank, and the people at the bank say that after one year, they will give me an additional :math:`\$10` at that time.  We say that they are paying :math:`10\%` interest for the year on the principal :math:`P` of :math:`\$100`.

However, suppose I bargain with them.  I get them to promise to pay me half the interest (:math:`5\%`) at the six-month mark, and the rest after one year.  My account will hold :math:`\$105` after six months, and the interest due for the second half will be :math:`5\%` of :math:`\$105`, which is :math:`\$5.25` for a total of :math:`\$10.25`.

The equation to describe this is that if the rate of interest is :math:`r` and the year is broken up into :math:`n` periods when interest will be paid, the total amount at the end will be:

.. math::

    A = P(1 + \frac{r}{n})^n

This is compound interest.  If there are additional years :math:`t`, the exponent will be :math:`nt` rather than :math:`n`.

It turns out, as we will see below, that 

.. math::

    (1+b)^{mn} = (1+bm)^n

It is a little counter-intuitive, but nevertheless true.  So in the equation

.. math::

    A = P(1 + \frac{r}{n})^n

the same factor can be either in the second term inside or up in the exponent.  So we bring out the factor :math:`r` and obtain

.. math::

    A = P(1 + \frac{1}{n})^{nr}

    A = P \ [ \ (1 + \frac{1}{n})^{n} \ ] ^r

And now we start wondering what happens if the bank pays every month :math:`r=12` or every day :math:`r=365` or every second.  What happens if the interest is compounded continuously?

.. math::

    A = \lim_{n \rightarrow \infty} P \ [ \ (1 + \frac{1}{n})^{n} \ ] ^r

This becomes the question, what is the value

.. math::

    A = \lim_{n \rightarrow \infty} (1 + \frac{1}{n})^{n}

It is going to turn out that this limit is equal to a number which is called :math:`e`

.. math::

    e = 2.71828\ 18284\ 59045 \dots