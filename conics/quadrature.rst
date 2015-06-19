.. _quadrature:

##########
Quadrature
##########

Here is a figure from wikipedia, showing a parabola and one of its chords (which could be drawn between any two points on the curve). 

A triangle is constructed from the chord: the point dividing the horizontal distance in half is found and that position is used for the x-value of the third point.

Archimedes showed that the total area underneath the parabola, bounded on the bottom in this figure by a line drawn through the two outside vertices of the triangle, is 4/3 of the area of the triangle itself. 

The method he used is called the "quadrature of the parabola" and it is (from our modern perspective) a relatively simple though still revolutionary idea.

.. image:: /figs/para_tri.png
       :scale: 25%

==================
Slope of the chord
==================

One simple, interesting consequence of this construction is that the slope of the tangent to the parabola at this midway point is equal to the slope of the chord.  That is where we will begin the proof.

The general equation of a parabola is :math:`y = ax^2 + bx + c` but for any given parabola, we can translate the figure to the origin (by :ref:`completing the square <parabola>`).  The parabola recentered at the origin with the same shape has the formula :math:`y = ax^2`.

Let's pick any two points on the parabola at coordinates :math:`x=u` and :math:`x=v`, the corresponding coordinates of the points are

.. math::

    P = (u, \ au^2)

    Q = (v, \ av^2)

.. image:: /figs/para_tri2.png
       :scale: 25%

:math:`P` is the right-hand point in the figure.  The slope :math:`m` of the chord that connects :math:`P` and :math:`Q` is

.. math::

    m =\frac{au^2 - av^2}{u - v} 
    
    = \frac{a(u^2-v^2)}{u - v} 
    
    = \frac{a(u-v)(u+v)}{u - v}
    
    = a(u + v)
    
We can see that this formula gives the correct answer for :math:`u = - v`, since the slope at the vertex is :math:`0`.  Now label the midpoint :math:`x=w`:

.. math::

    w = \frac{u + v}{2}
    
And the slope at :math:`w` is (from calculus or trigonometry)

.. math::

    f'(w) = 2aw = = 2a \ \frac{u+v}{2} = a(u + v)

So the proposition is correct.

====================
Area of the triangle
====================

Another interesting thing about this figure is that the area of the triangle can be found from the length of the vertical that comes down from the top, the part of it that stays inside the blue region:

.. image:: /figs/para_tri.png
       :scale: 25%

This line divides the big blue triangle into two smaller triangles that share this "base", :math:`b`.  They both have "height" :math:`d`, since :math:`w` was chosen as half way between :math:`u` and :math:`v`, so their areas are equal, and the total area of the two together is :math:`A = bd`.  This is the area of the large triangle.

However, we want to find an expression for the area only in terms of :math:`u` and :math:`v` (no :math:`b` or :math:`d`).  Let's look at a second version of the figure again below.  To repeat, what we found above is that the slope at the point on the parabola corresponding to :math:`x=w` is equal to the slope of the line that connects :math:`v` and :math:`u`, and more important to us now, that the area of the combined triangle (vertices :math:`u,v,w`) is

.. math::

    A = \frac{1}{2} (u-v) \ b
    
    = (u-w) \ b

where :math:`b` is the distance parallel to the :math:`y`-axis between the two points marked in gray.  

.. image:: /figs/para_tri2.png
       :scale: 25%

The length of the "base" :math:`b` is the average of the y-values for :math:`x=u` and :math:`x=v`, minus :math:`aw^2`.

.. math::

    b = \frac{1}{2}(au^2+av^2) - aw^2

and from before

.. math::

    w = \frac{1}{2}(u+v)
    
so we have

.. math::

    b = \frac{1}{2}(au^2+av^2) - a\ [\ \frac{1}{2}(u+v)\ ]^2
    
Factor out :math:`a/4`

.. math::

    = \frac{1}{4} a\ [\ 2u^2 + 2v^2 - (u+v)^2 \ ]

    = \frac{1}{4} a\ [\ 2u^2 + 2v^2 - u^2 - 2uv - v^2 \ ]
    
    = \frac{1}{4} a\ [\ u^2 - 2uv + v^2 \ ]

    b = \frac{1}{4} a\ (u-v)^2
    
The area is then

.. math::

    A = bd = \frac{1}{4} a \ (u-v)^2 \times \frac{(u-v)}{2}
    
    = \frac{1}{8} a \ (u-v)^3

=====
Check
=====

We can check some cases to see if this makes sense.  First if :math:`u = v` then the area is zero and :math:`w=u=v`, so that's good.  Second, if :math:`u = -v` then

.. math::

    A = \frac{1}{8} a\ (u-v)^3  = \frac{1}{8} a\  (2u)^3  = au^3
    
We compare this result with a direct computation by geometry.  In the figure we have two symmetric triangles with individual area 

.. math::

    \frac{1}{2} u \ au^2

The total area is twice that, so it checks.  Finally, suppose we have :math:`v = 0`

.. math::

    A = \frac{1}{8} a\  (u-v)^3
    
This one is harder to see, but we have that 

.. math::

    d = \frac{1}{2} (u-v) = \frac{1}{2}u
    
:math:`b` is the distance between the average :math:`y`-value which is :math:`(1/2)au^2` and :math:`aw^2 = a(u/2)^2`

.. math::

    b = a\   (\frac{1}{2}u)^2 - \frac{1}{2}\ [\ au^2-0\ ]\  = \ \frac{1}{4}a \ u^2

    A = bd = \frac{1}{8}au^3

so they all check.

==================
Draw new triangles
==================

The reason for the whole preceding argument is the following.  We found that the area of the triangle formed from two points on the parabola :math:`u` and :math:`v` and the point on the parabola with :math:`x`-value half-way between them is:

.. math::

    A = bd 
    
    = \frac{1}{8} a\ (u-v)^3 
    
    = k(u-v)^3, \ \ k = const

It is solely a function of :math:`u-v`.  So now let us we draw two new triangles (in light green).  

.. image:: /figs/para_tri3.png
       :scale: 25%

For each of these triangles the distance between the new vertices is one-half what we had before.  Everything that we have for the big blue triangle is also true for these two new ones, but just adjusted by a factor of :math:`u'-v' = (1/2)(u-v)`.

What this means is that the area of each light green triangle is in the ratio to the blue one of :math:`(1/2)^3 = 1/8`.  But there are two of these new triangles, so the total new area added is in the ratio :math:`1/4`.

Suppose we repeat the construction, making the yellow triangles.  The new area of each is in the ratio :math:`(1/4)^3 = 1/64` but there are now :math:`4` of these yellow triangles so the total area is in the ratio :math:`1/16 = (1/4)^2`.

Let the area of the original triangle be :math:`T`

Then, that of the light-green triangles is :math:`1/4 T`, adding blue and light-green together we obtain

.. math::

    A = T + \frac{1}{4} T
    
with the addition of the yellow triangles the total is

.. math::

    A = T + \frac{1}{4} T  + \frac{1}{16} T

If we carry out this process *ad infinitum* we have an infinite series:

.. math::

    A = T(1 + \frac{1}{4} + \frac{1}{16} + \cdots )

A visual proof (I believe it is Archimedes') that the sum of this series (not counting the first term) is :math:`1/3`.  

.. image:: /figs/para_series_sum.png
       :scale: 25%

So the total is :math:`4/3`, and the complete area under the parabola is :math:`4/3` the area of the triangle drawn as we described!

This called the "method of exhaustion."

===================
Solving our problem
===================

Application to the problem of the area "under" the curve :math:`y=x^2` is as follows.  Consider the parabola with its vertex at the origin.  Place two points on the parabola at :math:`x=-1` and :math:`x=1`.  The :math:`y`-values for both are :math:`1`.  The midpoint is then the vertex.  The area of the triangle formed from these three points is 

.. math::

    A = 1/2 \ \text{base} \times \text{height} 
    
    = 1/2 \times 2 \times 1 = 1

Therefore, the area "above" the parabola in this region is :math:`4/3`.

Now consider half of the region, from :math:`x=0` \rightarrow :math:`x=1`.  This is the unit square.  The area above the parabola in this region is :math:`2/3`, therefore, the area below the parabola is :math:`1 - 2/3 = 1/3`.





