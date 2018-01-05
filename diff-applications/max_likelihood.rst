.. _max_likelihood:

##################
Maximum likelihood
##################

A nice application of logarithmic differentiation is of a set of Bernoulli trials, like a series of coin flips where the coin isn't fair, but instead has a probability :math:`p` of coming up heads (H) and :math:`1-p` of coming up tails (T).

Note that this classic example is actually impossible to achieve.  One cannot "weight" a coin to do this, though it is easy with a die (singular of dice).

http://www.stat.columbia.edu/~gelman/research/published/diceRev2.pdf

Now, :math:`p` is unknown, but we have some data about how the coin performs, and we wish to use the data to estimate :math:`p` by the method of maximum likelihood.  We observe this sequence of trials:

.. math::

    HTHHTTTHTHHH

Theory says that the probability of observing this sequence of events is dependent on :math:`p` in the following way:

.. math::

    p(1-p)pp(1-p)(1-p)(1-p)p(1-p)ppp = p^7(1-p)^5

We call the probability of observing this data, *given* some underlying probability model :math:`p`, the likelihood :math:`L`:

.. math::

    L(p) = p^7(1-p)^5

And in general, since each trial is independent and identically distributed

https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables

we can write that for :math:`n` trials and :math:`k` successes we would have

.. math::

    L(p) = p^k(1-p)^{n-k}

Here, :math:`n` and :math:`k` are constants for any particular sequence, but we would like to have the general formula.
 
To find the maximum for :math:`L` we differentiate and set that equal to 0.

.. math::

    \frac{d}{dp} L = 0

However, we note that since :math:`\ln L` increases and decreases along with :math:`L`, the value of :math:`p` that gives a maximum for :math:`L` also gives a maximum for :math:`\ln L`.  So we will take the logarithm of :math:`L` and set *that* equal to zero:

.. math::

    \frac{d}{dp} \ln L = 0

    \ln L = k \ln p + (n-k) \ln(1-p)

Take the derivative :math:`d/dp` of both sides (we get a minus sign from the chain rule):

.. math::

    \frac{d}{dp} \ln L = 0 = \frac{k}{p} - \frac{n-k}{1-p}

    \frac{k}{p} = \frac{n-k}{1-p}

Multiply through by :math:`1-p` and also by :math:`1/k`:

.. math::

    \frac{1-p}{p} = \frac{n-k}{k}

    \frac{1}{p} = \frac{n}{k}

    p = \frac{k}{n}

As we might have guessed, the maximum likelihood estimate of :math:`p` is simply the ratio of the observed number of successes to the number of trials:  :math:`k/n`.
