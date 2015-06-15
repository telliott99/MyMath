.. _sphere:

####################
Volume of the sphere
####################

This first chapter of the applications section is about a discovery that is a precursor to the method we developed for integration.

Here we explore Archimedes' tremendous discovery about volumes.  He found a connection between the volume of the sphere, the cone and the cylinder, and was so proud of what he discovered that he had the sphere and cylinder engraved or somehow mounted on his tombstone.  Cicero searched for his grave and confirmed the description of the monument nearly 150 years later.

.. image:: /figs/sphere_cyl.png
       :scale: 25%

Perhaps most interesting, Archimedes said that he discovered the correct result by balancing the three objects on a fulcrum.  

.. image:: /figs/archimedes1.png
       :scale: 25%

We will analyze this figure a bit later.  

According to Archimedes (in *the Method*, translation by Heath)

    For certain things which first became clear to me by a mechanical method had afterward to be demonstrated by geometry...it is of course easier, when we have previously acquired by the method some knowledge of questions, to supply the proof than it is to find the proof without any previous knowledge. This is a reason why, in the case of the theorems the proof of which Eudoxus was the first to discover, namely, that the cone is a third part of the cylinder, and the pyramid a third part of the prism, having the same base and equal height, we should give no small share of the credit to Democritus, who was the first to assert this truth...though he did not prove it.

Let's consider the first figure shown above.  Start with a sphere of radius :math:`R`, which just fits inside a cylinder, also with radius :math:`R` and height :math:`2R`.  

.. image:: /figs/sphere_cyl.png
       :scale: 25%

The volume of this cylinder is 

.. math::

    V_{cylinder} = H \ \pi R^2 = 2R \ \pi R^2 = 2 \pi \ R^3


Now assuming the result we will derive, the volumes of a sphere and cone are

.. math::

    V_{sphere} = \frac{4}{3} \ \pi R^3

    V_{cone} = \frac{1}{3} \ \pi R^3

Thus, for this special cylinder and sphere

.. math::

    V_{cylinder} = V_{sphere} + 2 V_{cone}

where the cone is one with a radius and height of :math:`R`.

So what I would like you to do is to picture that sphere, with radius :math:`R`, just fitting into a cylinder with radius :math:`R` and total height :math:`2R`, and beside it a cone, and on top of that an inverted cone.  This pair of cones have a base that is the same as the base of the cylinder (and the central cross-section of the sphere), that is, a circle with radius :math:`R`.

Here is the top half of the picture.

.. image:: /figs/sphere_cone.png
       :scale: 25%

According to our formulas, the volume of the cone is

.. math::

    V_{cone} = \frac{1}{3} \ H \ \pi R^2 = \frac{1}{3} \ R \ \pi R^2

    = \frac{1}{3} \ \pi R^3

The volume of the sphere is :math:`V= 4/3 \pi R^3`, thus for the hemisphere we have :math:`V= 2/3 \pi R^3`, and the volume of the cylinder (with half the height of the one we first considered) is 

.. math::

    V_{cylinder} = H \ \pi R^2 = 2 \pi \ R^3

And the difference between the volume of the cylinder and the volume of the sphere is exactly equal to the volume of the two cones.  Of course, here we have used the formula for a sphere and the relationship with the cylinder.  What we'd like to know is find out how to prove this is true.

Using the idea of slicing volumes into thin sections, and then adding up the volumes of all the section, it is easy to see why this is so.  Let's look at our hemisphere (above) and an inverted cone having the same radius, :math:`R`.  

We consider a section through the sphere and the cone at some height :math:`h`, equal to the distance from the center of the bottom (center of the sphere, pointy end of the cone).  In the cone, by similar triangles, the horizontal distance :math:`r_c` for each slice is equal to :math:`h`.  In the sphere, the horizontal distance :math:`r_s` is equal to :math:`\sqrt{R^2 - h^2}`.

Then the areas of the slices are as follows.  For the sphere

.. math::

    r_s^2 = R^2 - h^2

    A = \pi r_s^2 = \pi (R^2 - h^2)

For the cone

.. math::

    r_c^2 = h^2

    A = \pi r_c^2 = \pi h^2

The sum of the areas is then

.. math::

    A_s + A_c = \pi (R^2 - h^2) + \pi h^2 =  \pi R^2

which is just the cross-sectional area of the cylinder.  So what we have discovered is that **for each slice, the areas add up**---cone plus sphere is equal to cylinder.  And since we know the volume of the cone is

.. math::

    V = \frac{1}{3} \pi R^3

and the volume of this half-cylinder (height = :math:`R`) is 

.. math::

    V = \pi R^3

the difference is the volume of the hemisphere

.. math::

    V = \frac{2}{3} \pi R^3

and the volume of the whole sphere is then

.. math::

    V = \frac{4}{3} \pi R^3

To say it in a different way (and switching to the more usual lower case :math:`r` for radius), the fundamental relationship here is that for a hemisphere, a cone, and a cylinder, all of radius :math:`r` and for the latter two, of height :math:`r`, the volumes of the cone and the hemisphere add up to that of the cylinder:  :math:`1/3 + 2/3 = 1`.  For a whole sphere, we need *two* cones of that dimension, and a double cylinder with its height extended to :math:`2r`.

Now, I read somewhere that what Archimedes actually balanced is a set-up like that shown here

.. image:: /figs/archimedes1.png
       :scale: 25%

There are three factors that complicate our calculation:  (i) we now have a single cone with radius :math:`2r` and height :math:`2r` (because it's doubled in both radius and height the cone's volume is increased by a factor of :math:`2^3`), (ii) the sphere and cone are twice as far from the fulcrum as the cylinder, and (iii) the cylinder is made out of something denser than the other objects (four times more dense).

Let :math:`\pi r^3` be one unit of volume, then the volumes are

.. math::

    \text{sphere} =   \frac{4}{3}

    \text{cone} =     \frac{1}{3} \times 8 = \frac{8}{3}

    \text{cylinder} = 2

That's :math:`12/3 = 4` for the sphere plus cone, and furthermore they count double since they are twice the distance from the fulcrum, giving :math:`8` in our volume units.  So the left side should be :math:`4 \times` the weight on the right side.  However, we are told that the density of the material for the cylinder was four times that of the objects on the left.  Hence, it all balanced.

I looked up some densities to try to guess what Archimedes used:

.. sourcecode:: bash

    sand    2.80
    copper  8.63
    silver  10.40
    gold    19.30
    marble  2.56

How about marble and silver?