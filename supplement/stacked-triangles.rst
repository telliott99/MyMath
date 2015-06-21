.. _stacked-triangles:

###############
Cosine of s + t
###############

====================
Geometric derivation
====================

Suppose we consider a right triangle, with one of the angles labeled :math:`s`.  Scale this triangle to any size you like, and all the different scaled triangles will be similar to each other, having the third angle complementary to :math:`s`, whose sum combined with :math:`s` is equal to :math:`\pi/2`.

Now construct another right triangle containing angle :math:`t`, and scale it so that the base adjacent to angle :math:`t` is exactly as long as the hypotenuse of the triangle containing angle :math:`s`, and then draw them stacked vertically as shown:

.. image:: /figs/sum_angle2.png
       :scale: 25%

The combined triangles are then both scaled so that the hypotenuse of the second triangle has unit length.

In addition to this construction, our second crucial insight is to draw vertical and horizontal dotted lines as shown.  Since the vertical line makes a right angle with the base, we have that:

.. math::

    s + t + u =  t + u + v

    s = v

Since I already know the result we are looking for, write

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

Our goal is to verify this eternal truth, with the help of the diagram.  Basically, we will run the derivation backward, from the formula above to the relationships shown.  We add some labels to the sides of the triangles and substitute into the above equation, using the figure for reference:

.. image:: /figs/sum_angle.png
       :scale: 25%

From the right panel of the figure

.. math::

    \cos s = \frac{a+b}{g}
    
    \cos t = \frac{g}{1}
    
    \cos s \cos t = a + b
    
Using the small triangle containing :math:`s` at the top:

.. math::

    \sin s = \frac{b}{h}

and 

.. math::

    \sin t = \frac{h}{1}
    
    \sin s \sin t = b

We use algebra to calculate:

.. math::

    \cos s \cos t - \sin s \sin t = (a + b) - b

And compare with what can be read directly from the figure

.. math::
 
    \cos s + t = a 
    
    = (a + b) - b

    = \cos s \cos t - \sin s \sin t

We have verified the formula, by working backward from it to true statements based on the figure.

As another quick check we can ask what happens to the formula 

.. math::

    \cos s + t = \cos s \cos t - \sin s \sin t

when :math:`t = 0`.  Then the first term is the cosine of :math:`s`, and the second term is equal to :math:`0`.

=================
Extension to sine
=================

Referring back to the diagram 

.. image:: /figs/sum_angle.png
       :scale: 25%

(and again, with our goal clearly in mind)

.. math::

    \sin s =  \frac{c}{g} \ \ \ \  \cos t = \frac{g}{1} \ \ \ \  \sin s \cos t = c

    \sin t = \frac{h}{1} \ \ \ \  \cos s = \frac{d}{h} \ \ \ \ \sin t \cos s = d

From the figure

.. math::

    \sin s + t = c + d 

substituting from above, we obtain

.. math::

    \sin s + t =  \sin s \cos t + \cos s \sin t

Using the even/odd function rules, we obtain

.. math::

    \sin s - t =  \sin s \cos t - \cos s \sin t 

You should try to commit at least one cosine and one sine formula to memory.  

They can easily be used to derive other formulas, like the double-angle formula.
