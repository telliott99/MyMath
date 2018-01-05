.. _kepler-feynman:

#######
Feynman
#######

Richard Feynman gave a famous series of talks at Cornell in 1964 that were videotaped and transcribed into a book.  Bill Gates later purchased the tapes and they are now available on the web on YouTube.  I still have the book, called *The Character of Physical Law*.  This argument is from Chapter 2, *The Relation of Mathematics to Physics*.

It depends on a tiny bit of calculus---specifically, the product rule for differentiation.  It also uses the fact that the product rule is valid for vector cross products.  (See :ref:`here <cross-product2>` for a proof and :ref:`here <cross-product>` for a general introduction to the cross-product).

The rule is that if we have two vectors :math:`\mathbf{a}` and :math:`\mathbf{b}` which are changing (i.e. some or all of their individual components are functions of time), then

.. math::

    \frac{d}{dt} \ (\mathbf{a} \times \mathbf{b}) = \frac{d\mathbf{a}}{dt} \times \mathbf{b} + \mathbf{a}  \times \frac{d\mathbf{b}}{dt}    

In our application the two vectors are the position vector of the planet with respect to the sun, :math:`\mathbf{r}`, and the time-derivative of that vector, which is just the velocity vector.

.. math::

    \frac{d\mathbf{r}}{dt} = \mathbf{v} 

Or, as the physicists would write it, using Newton's dot notation for the time-derivative:

.. math::

    \frac{d\mathbf{r}}{dt} = \mathbf{v} = \dot{\mathbf{r}}

We are interested in the area of the triangle formed by the vectors :math:`\mathbf{r}` and :math:`\dot{\mathbf{r}}` over a small interval of time.  The area swept out is constant, as Newton showed, and we will prove again here.

A nice feature of the vector cross-product is that it provides this area.  Namely

.. math::

    2A =  | \mathbf{r} \times \dot{\mathbf{r}} | = |\mathbf{r}| |\dot{\mathbf{r}}| \sin \theta   

where :math:`\theta` is the angle between :math:`\mathbf{r}` and :math:`\dot{\mathbf{r}}`, and :math:`A` is the little bit of additional area.  We will ignore the factor of :math:`2` in what follows (it would not alter the result).

The direction of the cross-product is perpendicular to both of the two input vectors:  in this case straight-up.  Since the force acts along :math:`\mathbf{r}`, the direction of the cross-product doesn't change during the motion.

Our hypothesis is that :math:`A` (the magnitude of the cross-product) is the same no matter where the planet is in its orbit.  Another way to say the same thing is that A doesn't change with time

.. math::

    \frac{d}{dt} \ A = \dot A = 0 

Now, as we said:

.. math::

    A = \mathbf{r} \times \dot{\mathbf{r}} 

and we want to compute :math:`\dot A`.  Using the product rule it's easy.

.. math::

    \dot A = \frac{d}{dt} \ (\mathbf{r} \times \dot{\mathbf{r}}) 

    \dot A = \dot{\mathbf{r}} \times \dot{\mathbf{r}} \ + \ \mathbf{r} \times \ddot{\mathbf{r}} 

As Feynman says: it's just playing with dots!  So let's look at those two terms.  Another nice fact about the cross-product is that if the two vectors point in the same direction, then their cross-product is zero.

Any vector certainly points in the same direction as itself, so the first term is zero.

.. math::

    \dot{\mathbf{r}} \times \dot{\mathbf{r}} \ = 0 

Next, recall that the second derivative of the position with respect to time is the acceleration vector.  According to Newton's second law, the force of gravity points toward the sun, radially.

But of course the position vector also points out radially from the sun.  :math:`\mathbf{r}` and :math:`\ddot{\mathbf{r}}` are in the same direction (the opposite direction *is* the same direction, multiplied by :math:`-1`), so the cross-product is again zero.

.. math::

    \mathbf{r} \times \ddot{\mathbf{r}} \ = 0 

So that means the whole thing is zero.

.. math::

    \dot A = \dot{\mathbf{r}} \times \dot{\mathbf{r}} \ + \ \mathbf{r} \times \ddot{\mathbf{r}} = 0 + 0 = 0  

We have shown that the area is constant, which is Kepler's second law.  By the way, the invariant quantity

.. math::

    \mathbf{r} \times \mathbf{v} = \mathbf{r} \times \dot{\mathbf{r}} 

(times the mass) is twice the angular momentum, and the lack of change is the principle of the conservation of angular momentum.
