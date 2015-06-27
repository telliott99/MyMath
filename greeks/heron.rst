.. _heron:

#####
Heron
#####

Once again, in the triangle below, A, B, and C are the angles, with side lengths a, b, and c.

.. image:: /figs/triangle.png
   :scale: 50 %

One other formula we want to prove is called Heron's Formula for the area of a triangle.  For this formula we don't need the altitude h or the parts of side c, which are  d and e.

If :math:`s` is the semi-perimeter

.. math::

    s = \frac{1}{2}(a + b + c) 

    A = \sqrt{s + (s-a) + (s-b) + (s-c)} 

Start with the well-known formula for area

.. math::

    A = \frac{1}{2} \ \text{base} \times \text{height} = \frac{1}{2} \ c \ h = \frac{1}{2} \ c b \sinA 

We will come back to this and substitute for the sine of A.  But first, rearrange the equation for the law of cosines

.. math::

    a^2 = c^2 + b^2 - 2bc \cos A 

    \cosA = \frac{(c^2 + b^2 - a^2)}{2bc} 

    \sinA = \sqrt{1 - \cos^2 A} = \sqrt{ 1 - \frac{(c^2 + b^2 - a^2)^2}{(2bc)^2}} 

So finally we have

.. math::

    A = \frac{1}{2}\  c \ b \ \sqrt{ 1 - \frac{(c^2 + b^2 - a^2)^2}{(2bc)^2}} 

    A = \frac{1}{4} \sqrt{4b^2c^2 - (c^2 + b^2 - a^2)^2} 

Now we just need to work on what is under the square root.  It looks like a mess but will simplify quite a bit.

For the next part, we won't write :math:` A = \frac{1}{4} \sqrt { \ldots }`, but we'll recall that it's there near the end, when we will write it as  :math:` A = \sqrt {\frac{1}{16} \ldots }`

Look at what's inside

.. math::

    4b^2c^2 - (c^2 + b^2 - a^2)^2 

This looks familiar, it is a difference of squares

.. math::

    (2bc + (c^2 + b^2 - a^2))(2bc - (c^2 + b^2 - a^2)) 

In the first term, we can rearrange

.. math::

    2bc + c^2 + b^2 - a^2 

    (c+b)^2 - a^2) 

    (c+b+a) (c+b-a) 

Similarly in the second term

.. math::

    -(c^2 - 2bc + b^2 - a^2) 

    -((c-b)^2 - a^2) 

    -((c-b+a) (c - b - a)) 

    (c-b+a) (a + b - c) 

Putting it all together, we have

.. math::

    (c + b + a) (c + b - a)(c - b + a) (a + b - c) 

Recall that the perimeter

.. math::

    p = a + b + c = 2s 

The first term above, :math:`(a + b + c)`, is the perimeter, that is, twice the semi-perimeter or :math:`2s`.  The second term is :math:`p - a - a = 2s - 2a = 2(s-a)`.  The third and fourth terms can be seen to be equal, by the same logic, to :math:`2(s-b)` and :math:`2(s-c)`.  Recalling the square root, etc. from above, we have finally:

.. math::

    A =  \sqrt {\frac{1}{16}  \ 2(s) 2(s-a) \ 2(s-b) \ 2(s-c)} 

Canceling

.. math::

    A =  \sqrt { s (s-a) (s-b) (s-c) } 

QED.

As a simple example, if we have a right triangle with sides 3,4,5, then the area is one-half of 3 times 4 = 6.  The semi-perimeter is s

.. math::

    s = \frac{(3 + 4 + 5)}{2} = \frac{12}{2} = 6 

We have

.. math::

    A =  \sqrt { 6 (6-5) (6-4) (6-3) } =  \sqrt { 6 (1) (2) (3) } = 6 
