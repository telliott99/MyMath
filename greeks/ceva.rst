.. _ceva:

##############
Ceva's Theorem
##############

=========
Midpoints
=========

I am putting this proof in the section on the Greeks, although Ceva was an Italian and lived much later, because it is a classical geometrical result.

We begin with the triangle shown below, picking a point :math:`P` to be any point inside the triangle.  Now draw line segments from each vertex through :math:`P` and extend them to the opposing side.

.. image:: /figs/ceva1.png
   :scale: 50 %

Since :math:`P` can be anywhere, the ratio can be anything. Let's call it :math:`x`.

.. math::

    BX/XC = x 

Line :math:`AX` divides the whole triangle into two parts.  We know that the area of :math:`\triangle ABX` is in the same proportion to the area of :math:`\triangle ACX` as :math:`x`, because they share the same height, while :math:`x` is the ratio of their bases.  Now consider the lower pair of triangles :math:`\triangle BPX` and :math:`\triangle CPX`

.. image:: /figs/ceva2.png
   :scale: 50 %

These two also have their areas in the ratio :math:`x`, for the same reason.

The two triangles formed by the difference between these two triangles (:math:`\triangle ABP` and :math:`\triangle ACP`) are shown here

.. image:: /figs/ceva3.png
   :scale: 50 %

Again, the same statement is true, and for the same reason.

So, altogether, we have that

.. math::

    \frac{|ABX|}{|ACX|} = \frac{|BPX|}{|CPX|} = \frac{|ABP|}{|ACP|} = x 

By the same reasoning, if :math:`y=CY/YA`

.. math::

    \frac{|BCP|}{|ABP|} = y 

and if :math:`z= AZ/ZB`

.. math::

    \frac{|ACP|}{|BCP|} = z 

Then

.. math::

    xyz = \frac{|ABP|}{|ACP|} \ \frac{|BCP|}{|ABP|} \ \frac{|ACP|}{|BCP|} 

But all terms cancel, so

.. math::

    xyz = 1 

And this is of course true not just for the areas but for the original line segments

.. math::

    xyz = \frac{BX}{XC} \ \frac{CY}{YA} \ \frac{AZ}{ZB} 

This proof also works in reverse,

.. math::

    xyz = 1 \iff \text{3 lines cross at point P} 

============
Simple Proof
============

I offer an alternative, unusual but extremely simple proof of Ceva's theorem.  Draw a triangle, draw lines from the vertices to the midpoints of the opposing sides, which seem to meet at a point, as we have been doing.  Then draw connections between the midpoints.  Like this:

.. image:: /figs/ceva_small2.png
   :scale: 50 %

You should notice something:  all four of the smaller triangles are congruent, and they are similar to the original triangle.  The center one is rotated by 180 degrees.

This result is easy to prove.  One way is to start by showing that the midpoint connectors are each parallel to a side of the original triangle.  After that employ the theorem about alternate angles of a line that crosses two parallel lines.

But the big picture here is that we've constructed a smaller, inverted triangle inside the original one.  Why not continue?  Follow the same procedure again, and again.  

In the limit as the procedure is repeated, the triangles become smaller and smaller, and they will still be centered at the original point where the midpoint lines appear to cross.  They vanish into one single point.  This completes the proof.

=========
Altitudes
=========

So now, for this triangle

.. image:: /figs/ceva4.png
   :scale: 50 %

if :math:`\alpha` is the angle at vertex :math:`A` and so on, then for example,

.. math::

    BX = AB \cos \beta 

and

.. math::

    \frac{BX}{XC} = \frac{AB \cos \beta}{AC \cos \gamma} 

    \frac{CY}{YA} = \frac{BC \cos \gamma}{AB \cos \alpha} 

    \frac{AZ}{ZB} = \frac{AC \cos \alpha}{BC \cos \beta} 

When we construct this ratio, all the terms cancel.

.. math::

    \frac{AB \cos \beta}{AC \cos \gamma} 

    \frac{BC \cos \gamma}{AB \cos \alpha} 

    \frac{AC \cos \alpha}{BC \cos \beta} = 1 

That means

.. math::

    \frac{BX}{XC} \ \frac{CY}{YA} \ \frac{AZ}{ZB} = 1 

Therefore, the 3 altitudes all cross at a single point.  That point is the orthocenter.
