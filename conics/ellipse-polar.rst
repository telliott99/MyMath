.. _ellipse-polar:

##########################
Ellipse, polar coordinates
##########################

When converting between polar coordinates and Cartesian coordinates, we can try to use the familiar identities:

.. math::

    x = r \cos t
    
    y = r \sin t
    
    r = x^2 + y^2
    
    t = \tan^{-1}(\frac{y}{x})

For a line:

.. math::

    t = b

is one solution!

=======
Ellipse
=======

In Cartesian or :math:`x,y`-coordinates the basic equations are that:

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

the foci are at :math:`\pm c` where

.. math::

    c^2 = a^2 - b^2

and 

.. math::
    
    c = ea

and if :math:`e = 0` we have just a circle because then

.. math::

    a^2 = b^2

Now, to go to polar coordinates, direct substitution from :math:`x = r \cos t` gives something too complicated.  What is done is to *shift* the ellipse so that
one focus is at the origin, rather than the center.  We'll look at a derivation in a little bit.

The equation is:

.. math::

    r = \frac{p}{1 - e \cos t}

where 

.. math::

    p = b^2/a
    
    e = c/a

If :math:`0 \le e < 1` and :math:`p > 0`, it's an ellipse.  Then, of course if e = 0, it's a circle.  And if :math:`e \ge 1`, it's a parabola or a hyperbola.  It's interesting to explore the possibilities with a graphing program:

.. image:: /figs/ellipse-e=0.6.png
   :scale: 50 %

Here we have:

.. math::

    r = \frac{p}{1 - e \cos t}

with :math:`e = 0.6`.  If the sign of the cosine term is changed, it puts the other focus at the origin.  And if we substitute sine for cosine, can you guess what happens?  Then the longer ("semi-major") axis is up-and-down.

===============
Shifted ellipse
===============

According to this reference

http://math.etsu.edu/multicalc/prealpha/Chap3/Chap3-2/part4.htm

we should use vectors.  What a great idea!

.. math::

    \mathbf{r} + (\mathbf{r} - 2c \mathbf{i}) = \text{const}
    

.. image:: /figs/ellipse-shifted.png
   :scale: 50 %

Recall that the length of the invariant "string" is

.. math::

    c + a + a - c = const = 2a

then

.. math::

    |\mathbf{r}| + |\mathbf{r} - 2c \mathbf{\hat{i}} | = 2a

Rearrange and square

.. math::

    (r - 2a)^2 = |\mathbf{r} - 2c \mathbf{\hat{i}} |^2 
    
    = (r \cos t - 2c)^2 + (r \sin t)^2

Multiply out

.. math::

    r^2 - 4ar + 4a^2 = r^2 \cos^2 t - 4rc \cos t + 4c^2 + r^2 \sin^2 t

    -4ar + 4a^2 = - 4rc \cos t + 4c^2

    -ar + a^2 = - rc \cos t + c^2

Rearrange:

.. math::

    a^2 - c^2 = r(a - c \cos t)

Recall that :math:`b^2 = a^2 - c^2`

.. math::

    b^2 =  r(a - c \cos t)

    r = \frac{b^2}{(a - c \cos t)}

divide both top and bottom by :math:`a`

.. math::

    r = \frac{b^2/a}{1 - c/a \cos t}

Define

.. math::

    p = b^2/a
    
    e = c/a

then

.. math::

    r = \frac{p}{1 - e \cos t}

What Strang will give us is:

.. math::

    \frac{1}{r} = C - D \cos\theta

I can live with that.