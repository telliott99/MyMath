.. _ellipse-polar:

############################
Ellipse in polar coordinates
############################

When converting between polar coordinates and Cartesian coordinates, we will use the familiar identities:

.. math::

    x = r \cos t
    
    y = r \sin t
    
    r = x^2 + y^2
    
    t = \tan^{-1}(\frac{y}{x})

=======
Ellipse
=======

In Cartesian or :math:`x,y`-coordinates the basic equation is:

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = 1

One way to think about this equation is to say that if :math:`x` is "re-scaled" to :math:`x/a` and similarly, :math:`y` is re-scaled to :math:`y/b`, then we obtain a unit circle.

the *foci* are at :math:`\pm c` where

.. math::

    c^2 = a^2 - b^2

To derive this, consider the point at :math:`(a,0)`.  The combined distances to the foci are :math:`a + c` and :math:`a - c`.  The total length, which is a constant, is equal to :math:`2a`.  

Now consider the point at :math:`(0,b)`.  The length to each focus is just equal to :math:`a` (because the lengths are equal and combined they make :math:`2a`).

We can also calculate from Pythagoras that the square is equal to:

.. math::

    a^2 = b^2 + c^2

We also introduce :math:`e` for the *ellipticity* of the ellipse, where

.. math::
    
    c = ea

:math:`e` is the fraction of the length :math:`a` that we go out from the center to each focus :math:`c`.

and if :math:`e = 0` we have just a circle and then

.. math::

    a^2 = b^2

Now, to switch to polar coordinates, direct substitution from :math:`x = r \cos t` gives something too complicated.  

What is done is to *shift* the ellipse so that one focus is at the origin, rather than the center.  We'll look at a derivation in a little bit.

The equation is then:

.. math::

    r = \frac{p}{1 - e \cos t}

where 

.. math::

    p = b^2/a
    
    e = c/a

If :math:`0 \le e < 1` and :math:`p > 0`, it's an ellipse.  Then, of course if e = 0, it's a circle.  

And if :math:`e \ge 1`, it's a parabola or a hyperbola.  It's interesting to explore the possibilities with a graphing program:

.. image:: /figs/ellipse-e=0.6.png
   :scale: 50 %

In the figure we have:

.. math::

    r = \frac{1}{1 - e \cos t}

with :math:`e = 0.6`.  If the sign of the cosine term is changed, the other focus is at the origin.  And if we substitute sine for cosine, can you guess what happens?  Then the longer ("semi-major") axis is up-and-down.

===============
Shifted ellipse
===============

According to this reference

http://math.etsu.edu/multicalc/prealpha/Chap3/Chap3-2/part4.htm

we should use :ref:`vectors <vector-intro>`.  What a great idea!

The combined distances to the two foci from any point is a constant.  We express that constraint in vector form as

.. math::

    \mathbf{r} + (\mathbf{r} - 2c \mathbf{i}) = \text{constant}
    

.. image:: /figs/ellipse-shifted.png
   :scale: 50 %

Recall that the invariant "string" length is equal to :math:`2a` and so

.. math::

    |\mathbf{r}| + |\mathbf{r} - 2c \mathbf{\hat{i}} | = 2a

The components of :math:`\mathbf{r}` are:

.. math::

    \mathbf{r} = \ \langle r \cos t, r \sin t \rangle

and its length is just :math:`r`, or if you prefer:

.. math::

    |\mathbf{r}| = \sqrt{(r \cos t)^2 + (r \sin t)^2} = r
    
Rearrange and square

.. math::

    (2a - r)^2 = |\mathbf{r} - 2c \mathbf{\hat{i}} |^2 
    
Now:

.. math::

    \mathbf{r} - 2c \mathbf{\hat{i}} = \ \langle r \cos t - 2c, r \sin t \rangle 
    
    |\mathbf{r} - 2c \mathbf{\hat{i}} |^2 = (r \cos t - 2c)^2 + (r \sin t)^2

Combining:

.. math::

    (2a - r)^2 = (r \cos t - 2c)^2 + (r \sin t)^2

Multiply out

.. math::

    4a^2 - 4ar + r^2 = r^2 \cos^2 t - 4rc \cos t + 4c^2 + r^2 \sin^2 t

    4a^2 - 4ar = - 4rc \cos t + 4c^2

    a^2 - ar = - rc \cos t + c^2

Rearrange:

.. math::

    a^2 - c^2 = r(a - c \cos t)

Recall that :math:`b^2 = a^2 - c^2`

.. math::

    b^2 =  r(a - c \cos t)

    r = \frac{b^2}{(a - c \cos t)}

divide both top and bottom by :math:`a`

.. math::

    r = \frac{b^2/a}{1 - c/a \ \cos t}

Define

.. math::

    p = \frac{b^2}{a}
    
    e = \frac{c}{a}

then

.. math::

    r = \frac{p}{1 - e \cos t}

What Strang will give us is:

.. math::

    \frac{1}{r} = C - D \cos\theta

I can live with that.

.. math::

    r = \frac{p}{1 - e \cos t}

    1 - e \cos t = \frac{p}{r}
    
    \frac{1}{p} - \frac{e}{p} \cos t = \frac{1}{r}
    
    \frac{a}{b^2} - \frac{c}{b^2} \cos t = \frac{1}{b^2} (a - c \cos t) = \frac{1}{r}
    
As :math:`c \rightarrow a`, then :math:`r \rightarrow \infty` for :math:`\cos t = 1`.

=============================
Back to Cartesian coordinates
=============================

The equation we generated for the ellipse in polar coordinates was

.. math::

    r = \frac{p}{1 - e \cos t}

where :math:`p = b^2/a` and :math:`e = c/a`

Rearrange it slightly:

.. math::

    r (1 - e \cos t) = p
    
    r = p + e r \cos t
    
Since :math:`x = r \cos t`: we can get rid of the variable :math:`t`:

.. math::

    r =  p + ex

and then square both sides

.. math::
    
    r^2 = p^2 + 2pex + e^2 x^2

And since :math:`r^2 = x^2 + y^2`:

.. math::

    x^2 + y^2 = p^2 + 2pex + e^2 x^2

So we obtain

.. math::

    (1-e^2) x^2 - 2pex + y^2 = p^2

We will remove the :math:`x` term by completing the square, but before we do that, let's explore some simplifications.  The factor :math:`(1 - e^2)` becomes much better when multiplied by :math:`a^2`:

.. math::

    a^2 (1-e^2) = a^2 (1 - \frac{c^2}{a^2}) = a^2 - c^2 = b^2
    
and

.. math::

    pe = \frac{b^2}{a} \ \frac{c}{a} = \frac{b^2}{a^2} \ c
    
Multiplying by :math:`a^2` will help with that as well.
    
So let's go back to the equation and try multiplying through by :math:`a^2`:

.. math::

    a^2 \ [ \ (1-e^2) x^2 - 2pex + y^2 \ ] \ = a^2 p^2

    b^2 x^2 - 2 b^2 c x + a^2 y^2 = a^2 p^2
    
Divide by :math:`b^2`:

.. math::

    x^2 - 2cx + a^2 \ \frac{y^2}{b^2} = \frac{a^2}{b^2} \ p^2
    
Now complete the square by adding :math:`c^2` to both sides and we get:

.. math::

    (x - c)^2 + a^2 \ \frac{y^2}{b^2} = \frac{a^2}{b^2} \ p^2 + c^2

Divide by :math:`a^2`:

.. math::

    \frac{(x - c)^2}{a^2} + \frac{y^2}{b^2} = \frac{p^2}{b^2} + \frac{c^2}{a^2}

On the left-hand side, we have a standard ellipse in Cartesian coordinates, just offset to have its *center* at :math:`(c,0)`.  That is equivalent to placing the *left focus* (:math:`F1`) of the ellipse at the origin, as we did originally to generate the polar form (previous section).

I'm betting that the right-hand side is equal to :math:`1`.  Let's see if we can get there.

.. math::

    \frac{p^2}{b^2} + \frac{c^2}{a^2} = \frac{b^4}{a^2 b^2} + \frac{c^2}{a^2}
    
    = \frac{b^2}{a^2} + \frac{c^2}{a^2}
    
    = \frac{b^2 + c^2}{a^2}
    
    = \frac{a^2 - c^2 + c^2}{a^2} = 1

Yay.
    