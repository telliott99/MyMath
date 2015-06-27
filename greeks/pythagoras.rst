.. _pythagoras:

###################
Pythagorean Theorem
###################

The most famous theorem of Greek geometry is also the most useful in Calculus.  

.. image:: /figs/pythagoras.png
   :scale: 50 %

Here are some proofs.

First is a visual proof:

.. image:: /figs/pythagoras1.png
   :scale: 50 %

It really needs no explanation, but ..

In the left panel we have a large square box that contains a square whose side is also the hypotenuse of the four identical right triangles contained inside.  The area of most interest is in white.  Altogether the four triangles plus the white area adds up to the total.

We simply rearrange the triangles.  Now we evidently have the same area left over from the four triangles, because they still have the same area and the box has not changed.  

But clearly, now the white area is the sum of the squares on the second and third sides of the triangles.  Hence the two white squares on the right are equal in area to the large white square on the left.

The second proof relies on the following construction (Euclid :math:`I.47`, sometimes called the "bridal chair"), where the central triangle is a right triangle, and the other constructions are squares.

.. image:: /figs/pythagoras2.png
   :scale: 50 %

What we will show is that the part of the large square in red is equal in area to the entire small square, in maroon.

We label some points as shown:

.. image:: /figs/pythagoras3.png
   :scale: 50 %
   
We drop a vertical line :math:`EHG`, constructing the rectangle :math:`AFGH`.
   
Finally we sketch dotted lines for the long sides of two triangles:

.. image:: /figs/pythagoras4.png
   :scale: 50 %

What we will show is that triangle :math:`\Delta ABC` is congruent with triangle :math:`\Delta AEF`.  

We use "side-angle-side".  The two sets of sides are evidently equal 

.. math::

    AB = AE

    AC = AF

What about the included angle?  Both angle :math:`\angle BAC` and :math:`\angle EAF` contain right angles plus a shared angle in the middle (:math:`\angle EAC`).  So they are themselves equal, and thus we have proved the congruence relationship:

.. math::

    \Delta ABC = \Delta EFG

The next to last part of the proof is to see that triangle :math:`\Delta ABC` has base :math:`AB` and altitude :math:`AE` so its area is half that of the small square :math:`ABDE`.  On the other hand triangle :math:`\Delta AEF` has base :math:`AF` and altitude :math:`AH` (and :math:`FG`) so its area is half that of the rectangle :math:`AFGH`.  Hence we have proved that the two colored areas in this figure are equal:

.. image:: /figs/pythagoras2.png
   :scale: 50 %

Finally, we could proceed to do the same thing on the other side of the figure, but we just appeal to symmetry.  All the equivalent relationships will hold.

The third proof is an algebraic one.  We divide a right triangle into two smaller ones by dropping an altitude.

.. image:: /figs/triangle.png
   :scale: 50 %

By complementary angles, these three triangles are all similar (e.g., the angle between sides :math:`b` and :math:`h` is equal to that between sides :math:`a` and :math:`c`).  So we can construct ratios of sides that are equal.

We need a relationship involving :math:`a^2`.  We look for those with :math:`c` and :math:`e`:

.. math::

    \frac{e}{a} = \frac{a}{c}
    
    a^2 = ce

and something involving :math:`b^2`:

.. math::

    \frac{b}{d} = \frac{c}{b}
    
    b^2 = cd

Putting the two together:

.. math::

    a^2 + b^2 = ce + cd
    
    = c (d+e) = c^2

Which is what we wanted to prove.
