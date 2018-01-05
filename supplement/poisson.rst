.. _poisson:

####################
Poisson distribution
####################

The Poisson distribution is a special case of the well-known binomial distribution for Bernoulli trials.  It is an approximation for situations in which the probability of success :math:`p` on each trial is small, and the number of trials :math:`n` is large, so that the mean :math:`\lambda = np` of successes is not too much greater than :math:`1` for the sequence of trials taken as a whole.

Recall that the binomial distribution for the number of successes :math:`k` on :math:`n` trials, with probability :math:`p` of success on each trial is:

.. math::

    P(k) = {n\choose k} \  p^k \  (1-p)^{n-k}

where

.. math::

    {n\choose k} =  \frac{n!}{k!  \ (n-k)!}

Briefly, the derivation of this formula is that in independent trials with probability of success :math:`p` and of failure :math:`q`, for a particular series of successes and failures, say:

.. math::

    \textbf{SSFSSFFFFSSFF}

the probability of that *particular sequence* of results is

.. math::

    P = ppqppqqqqppqq = p^6 q^7

but more generally, for :math:`k` successes in :math:`n` trials

.. math::

    P = p^k q^{n-k}

Since :math:`q = 1-p`

.. math::

    = p^k (1-p)^{n-k}

The factor of

.. math::

    \frac{n!}{ k! \ (n-k)! }

which is :math:`\ge 1`, recognizes the occurrence of the combinations, that is, all the permutations of 

.. math::

    \textbf{SSFSSFFFFSSFF}

such as 

.. math::

    \textbf{SSSSSSFFFFFFF}

that have the *same* number of total successes.  Each of these contributes to the probability of :math:`k` successes in :math:`n` trials---see :ref:`here <combinations>` and 
 
http://en.wikipedia.org/wiki/De_Finetti's_theorem

======================
Simplifying n choose k
======================

The first step involves the "choose" or combinations term. We are interested in applications where :math:`n` is large and :math:`p` is small, and the mean number of successes is roughly near :math:`1`.  For :math:`k=2`

.. math::

    {n\choose 2} =  \frac{n!}{k!  \ (n-k)!}

    = \frac{ n (n-1)}{k!} \ \frac{(n-2) (n-3) \cdots}{(n-2) (n-3) \cdots}

    = \frac{ n (n-1) }{ k! }

Since :math:`n` is large

.. math::

    {n\choose 2} = \frac{ n (n-1) }{ k! } \approx \frac{n^2}{2!}

and more generally

.. math::

    {n\choose k} \approx \frac{n^k}{k!}

++++++
part 2
++++++

The other term we will modify is

.. math::

    (1-p)^{n-k}

    = \frac{(1-p)^n}{(1-p)^{k}}

The probability :math:`p` is quite small, but because :math:`n` is very large, we cannot just set :math:`1-p` equal to :math:`1` for the numerator, :math:`(1-p)^n`.

In contrast, if :math:`k` is a modest size (say, :math:`k < 10`), we can reasonably set :math:`1-p \approx 1` for the second term, and thus the denominator is equal to :math:`1`. The first term contributes much more than the second to the value for this expression.

Finally, we will show that :math:`(1-p)^n \approx e^{-np}`.

Recall that

.. math::

    e^x = 1 + x + \frac{x^2}{2!} + \cdots \approx 1 + x

(for small :math:`x`)

Since :math:`|p|` is small, we have

.. math::

    e^{-p} \approx 1 - p

so

.. math::

    (1-p)^n \approx (e^{-p})^n = e^{-np}

Alternatively, we note that the binomial expansion (for :math:`x` near zero) is

.. math::
 
    (1 + x)^n \approx 1 + x

by a Taylor series.  Since both :math:`(1-p)^n` and :math:`e^{-p}` are approximately equal to :math:`1-p` they are approximately equal to each other.

++++++++++++
Finishing up
++++++++++++

Substituting, we get

.. math::

    P(k) = {n\choose k} \  p^k \  (1-p)^{n-k}

    P(k) \approx \frac{n^k}{k!} \ p^k \ e^{-np}

We introduce a symbol for the mean, :math:`\lambda = np`

.. math::

    P(k) \approx \frac{\lambda^k}{k!} \ e^{-\lambda}

This is the Poisson distribution for the number of successes :math:`k` in :math:`n` Bernoulli trials where the mean number of successes :math:`\lambda = np` over the whole series of trials is small.

=========================
The Poisson is normalized
=========================

The Poisson distribution is normalized, meaning that it sums to :math:`1`, and so is a proper probability distribution.

.. math::

    \sum\limits_{k=0}^{\infty} \frac{\lambda^k}{k!} \ e^{-\lambda} = e^{-\lambda} \ \sum\limits_{k=0}^{\infty} \frac{\lambda^k}{k!} = 1

since

.. math::

    \sum\limits_{k=0}^{\infty} \frac{{\lambda}^k}{k!} = \frac{{\lambda}^0}{0!} + \frac{{\lambda}^1}{1!} + \frac{{\lambda}^2}{2!} + \cdots  = e^{\lambda}


+++++++
Symbols
+++++++

I've always used different symbols (from David Freifelder's *Molecular Biology*), although the ones shown above are standard in statistics.  In his notation the mean is :math:`m` and the number of successes is :math:`i` so the equation is

.. math::

    P(i) = \frac{e^{-m} \ m^i }{ i! }

which I actually can remember as "Emmy!" or more exactly, "emmii!".

An important property of the Poisson distribution is that it always simplifies dramatically for :math:`P(0)`, and also for :math:`P(1)` in the case where the mean is equal to :math:`1`.

.. math::

    P(i) = \frac{e^{-m} \ m^i }{ i! }

    P(0) = \frac{e^{-m} \ m^0 }{ 0! }

    P(0) = e^{-m}

When the mean is one, :math:`m = 1`

.. math::

    P(0) = \frac{1}{e}

    \approx 0.368

and 

.. math::

    P(1) = \frac{e^{-1} \ 1^1 }{ 1! } = \frac{1}{e}

For example, if we have a box that is divided into one hundred compartments, and if it were possible to throw one hundred marbles into it at random (equal probability for each bin), then at the end of the experiment slightly more than :math:`1/3` of the compartments will still be empty, an equal number will contain one marble, and about 25 percent will contain more than :math:`1`.

(Grinstead and Snell:

http://www.dartmouth.edu/~chance/teaching_aids/books_articles/probability_book/book.html

use the example of V1 rockets aimed at the city of London, on page 191).


The same holds for a bacterial culture infected with virus (such as phage T1) at a ratio of one virus particle per bacterial cell.  At an "moi" of :math:`1` (moi is short for "multiplicity of infection"), more than one-third of the cells will be uninfected.

Here is a plot of the Poisson distribution for selected values of :math:`\lambda` (:math:`m = 1,2,5,10`).

.. image:: /figs/poisson.png
   :scale: 50 %

Note the *very* small values for :math:`P > 10` when :math:`m < 5` (red, green, and blue).  That's the inverse factorial talking.

http://telliott99.blogspot.com/2010/02/replot-poisson-example-with-python.html

========
Genetics
========

One application is to bacterial genetics.  In the famous Luria-Delbruck experiment, mutant bacteria resistant to the action of the bacterial virus T1 were selected.  A modern (Darwinian) view appreciates that the mutations which confer virus-resistance pre-exist in the population, having occurred randomly during growth.  

An alternative, the Lamarckian view, suggests that the mutations arise *in response* to each bacterium's encounter with the virus.

So if we have an agar plate whose surface contains :math:`10^8` bacterial cells and a modest excess of virus particles, we can model the Lamarckian view as a process in which each individual cell has a very small probability of surviving the phage infection to which it is subjected, but the large number of cellular interactions with virus constitutes a large number of trials.

We adjust the mean number of successes (phage-resistant colonies per plate) to be near :math:`1`.  Then, the prediction is that the Poisson approximation will apply.  In particular, if :math:`f` is the fraction of plates which have no resistant colonies, then in

.. math::

    P(i=0) = \frac{e^{-m} \ m^i }{ i! }

both :math:`m^i` and :math:`i!` equal :math:`1` and so

.. math::

    P(i=0) = f = e^{-m}

    m = - \ln f

For example, if :math:`f=0.5`, then :math:`m=0.69`.  Now we can calculate :math:`P(i=1)`, :math:`P(i=2)`, and the whole distribution.  Here is the probability distribution for :math:`m=1` and :math:`i=0 \dots 5`:

.. math::

    \begin{matrix}
    0 & 0.368 \\
    1 & 0.368 \\
    2 & 0.184 \\
    3 & 0.061 \\
    4 & 0.015 \\
    5 & 0.003 \\
    \end{matrix}

and here is the cumulative probability distribution:

.. math::

    \begin{matrix}
    0 & 0.368 \\
    1 & 0.736 \\
    2 & 0.92 \\
    3 & 0.981 \\
    4 & 0.996 \\
    5 & 0.999 \\
    \end{matrix}

The probability of observing 6 or more colonies is less than :math:`1/1000`.

Crucially, this is *not* what one observes.  Instead, trials (plates) containing dozens or even hundreds of colonies are obtained at a frequency of about :math:`1` trial in :math:`10`.  These are Luria's "jackpots."

.. image:: /figs/Luria-Delbruck-Fig2.png
   :scale: 50 %

http://www.genetics.org/content/28/6/491.full.pdf+html

http://www.amazon.com/Slot-Machine-Broken-Test-Tube/dp/0060152605

In summary, the results are inconsistent with the Lamarckian view, but are easily explained by a model in which mutations occur randomly with respect to each cell division.  If a mutation happens to occur early in the growth of a culture, that mutant cell will have a large number of descendants, each of which can form a phage-resistant colony.

https://en.wikipedia.org/wiki/Luria–Delbrück_experiment