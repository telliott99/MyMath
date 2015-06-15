.. _combinations:

############
Combinations
############

Most people have heard an explanation of permutations somewhere in a math class.  Suppose we consider just the two letters :math:`a` and :math:`b`.  These can be arranged in two orders, or permutations.  Either :math:`a` is first and :math:`b` second, or the reverse:

.. math::

    ab
    
    ba

Either I eat pizza and then I eat ice cream, or I eat ice cream first and then pizza.

Now, how about :math:`abx`?

One way to reason about this is to say that in starting with a sequence of length two like :math:`ab`, there are three possible places to add a new letter---in front of or behind :math:`ab`, or between the two characters.  So starting with :math:`ab` we would have

.. math::

    xab \ \ axb \ \ abx

and starting with :math:`ba` we would have

.. math::

    xba \ \ bxa \ \ bax

so that's a total of :math:`3 \times 2 = 6` possibilities.

Another way is to imagine a row of three boxes, where each box will hold a particular letter.  We pick one of the three letters for the first position (the first box), one of the two remaining for the second position, and for the third, we have no choice.

In general, for :math:`n` objects, there are :math:`n \times n-1 \times \cdots \times 1 = n!` possible orders.

I have 5 Bob Marley CDs.

There are :math:`5! = 5 \times 4 \times 3 \times 2 \times 1 = 120` orders in which I could play my five CDs tonight.  I want to hear them all, but I don't want to hear any particular CD more than once.  Here are two of the 120 possible orderings.

.. image:: /figs/bob.png
   :scale: 50 %

Now, suppose we consider the problem of picking not all :math:`n` objects in order, but instead a subset of :math:`k` objects from that total :math:`n`.  For example, let's pick two CDs from the 5 above.

We could pick *Burning* and *Live*, or another group of 2 like *Catch A Fire* and *Natty Dread*.

It's easy to see that the number of possibilities in this problem is :math:`5 \times 4`, \emph{as long as the order is important}.

But suppose we don't want to do that.

Instead, we want to say that (*Catch A Fire*, *Natty Dread*) is the same as (*Natty Dread*, *Catch A Fire*).  We like Bob Marley, but listening to the same album twice in one night is just too much.  These are called "combinations."

Let's look at it with letters.  Suppose we have :math:`n=5` letters :math:`abcde` and we want to pick just :math:`k=2`.  We can pick any of :math:`5` for the first, then any one of the four remaining so there are :math:`5 \times 4 = 20` possibilities, when considering the ordered pairs.

.. math::

    ab \ \ ac \ \ ad \ \ ae
    
    ba \ \ bc \ \ bd \ \ be
    
    ca \ \ cb \ \ cd \ \ ce
    
    da \ \ db \ \ dc \ \ de

    ea \ \ eb \ \ ec \ \ ed

How many duplicates are there?  For every pair like :math:`x,y`, the reverse ordering :math:`y,x` is also present.

For any ordering of :math:`k` items, there are :math:`k!` permutations (all the permutations of different orderings but containing exactly the same elements).  

**We will have to correct our count by dividing by** :math:`k!`.

In general, if we have :math:`n` total items and choose :math:`k` of them, we have :math:`k` terms multiplied together starting with :math:`n \times (n-1) \times  \cdots`:

.. math::

    n \times (n-1)

    5 \times 4 =  20

To get the number of combinations we divide by :math:`k!`, which here equals :math:`2`, giving us :math:`10` combinations of :math:`k=2` objects from a total collection of :math:`n=5` objects.

A second issue is how we compute the number of orders.  To get :math:`k` terms from :math:`n` total objects, we do

.. math::

    n \times (n-1) \cdots \times (n-k+1)

It's a bit tricky, but I hope it is clear that for :math:`k=2` the last term is :math:`n-2+1 = n-1` and for :math:`k=3` the last term is :math:`n-3+1 = n-2` and so on.

In summary, to count the combinations with :math:`k` items picked from a set of :math:`n` total items

.. math::

    C = \frac{1}{k!} \ \ n \times (n-1) \cdots \times (n-k+1)

That's basically it, but we can simplify by considering one last thing.

.. math::

    n! = n \times (n-1) \cdots \times (n-k+1) \times (n-k) \cdots \times 2 \times 1

so

.. math::

    \frac{n! }{(n-k)!} = \frac{n \times (n-1) \cdots \times (n-k+1)}{1} \times \frac{(n-k) \cdots \times 2 \times 1}{(n-k) \cdots \times 2 \times 1 }
    
    = n \times (n-1) \cdots \times (n-k+1)

Therefore, we can rewrite the expression for :math:`C` above

.. math::

    C = \frac{1}{k!} \ \ n \times (n-1) \cdots \times (n-k+1)
    
    = \frac{n!}{k! \ (n-k)!}

This is commonly written 

.. math::

    C = {n \choose k} = \frac{n!}{k! \ (n-k)!}

Notice the symmetry

.. math::

    {n \choose k} = \frac{n!}{k! \ (n-k)!} = {n \choose n-k}

If I pick two cards from a deck of :math:`52`, that is the same problem as picking :math:`50` out of :math:`52`, because all I really need to do for the latter  is to discard the two to leave behind.
