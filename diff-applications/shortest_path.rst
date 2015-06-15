.. _shortest_path:

#############
Shortest path
#############

As shown in the figure below, we have two points :math:`P` and :math:`Q`, which might be, say, the origin and destination of a journey that must also go to the river (horizontal line at the top).  The point where we reach the river can be adjusted, and we seek the path that has the shortest overall distance.

.. image:: /figs/short1.png
   :scale: 50 %

There is a hard way to do this problem, and an easy way.  The hard way involves a tiny bit of calculus (to do the minimization).  I'll show that one first.  

Depending on where we put the point on the river, we have a horizontal distance :math:`x` to that point from :math:`Q`, and a horizontal distance :math:`d-x` to the same point from :math:`P`.

The path consists of two parts, from :math:`P` to the river, and from the river back to :math:`Q`.  That distance is

.. math::

    \sqrt{p^2 + (d-x)^2} + \sqrt{q^2 + x^2}

We take the derivative with respect to :math:`x`.  It's a little tricky.  For the first term, we get the denominator from applying the power rule to the square root (and a factor of :math:`1/2`), then we apply the chain rule to :math:`(d-x)^2` and get :math:`d-x` in the numerator, and finally a factor of :math:`-2`.  The twos cancel.  The second term is easier.  Set the result equal to :math:`0`

.. math::

    - \frac{d-x}{\sqrt{p^2 + (d-x)^2}} +  \frac{x}{\sqrt{q^2 + x^2}} = 0

    \frac{x}{\sqrt{q^2 + x^2}} = \frac{(d-x)}{\sqrt{p^2 + (d-x)^2}}

Now it's just algebra.

.. math::

    \frac{x^2}{q^2 + x^2} = \frac{(d-x)^2}{p^2 + (d-x)^2}

invert and simplify

.. math::

    \frac{q^2}{x^2} + 1 = \frac{p^2}{(d-x)^2} + 1

cancel :math:`+1` and take square roots

.. math::

    \frac{q}{x} = \frac{p}{(d-x)}

The result is that the two triangles should be similar (since their sides are in proportion and they are both right triangles).  

.. image:: /figs/short1.png
   :scale: 50 %

Another way to say it is that the angle where we come from :math:`P` to the river, and the angle by which we leave the river to :math:`Q` should be equal.

Now for the easy way.

.. image:: /figs/short2.png
   :scale: 50 %

We draw a vertical up the same distance :math:`q` to point :math:`Q'`---the mirror image of :math:`Q`.  Minimizing the distance to :math:`Q'` is the same problem because it's exactly the same distance.

What's the shortest distance between two points?  A straight line from :math:`P` to :math:`Q'`.  With a straight line then the two angles :math:`\phi` and :math:`\theta` are equal and the similarity of the triangles follows immmediately.

This is a famous result in physics.  It's true for light rays, that when you shine a light from :math:`P` at a mirror, the light rays arriving at :math:`Q` come by the shortest path.  The law about the angles being equal is called the "law of reflection" and it was known to Euclid.

Many pool players who know nothing about about Euclid know this result, and they use it all the time in making bank shots.

But this is only the beginning.  The general principle is called "least action."
