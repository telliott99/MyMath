.. _parabola-more:

###############
Parabola:  more
###############

===================
Focus and directrix
===================

.. image:: /figs/para3.png
   :scale: 50 %

A classical result about parabolas concerns the focus and the directrix.  The directrix is defined as a horizontal line passing below the parabola, and the focus as a point on the axis of symmetry above the vertex.

These are positioned so that the distance :math:`c` from the vertex to the focus is the same as the distance from the vertex vertically down to the directrix.  (This :math:`c` is *not* the same as the one in the standard formula for a parabola).

We haven't said yet what the value of :math:`c` is. The claim is that for the correct value of :math:`c`, the distance from any point on the parabola to the focus will be equal to the distance vertically down to the directrix.

The parabola shown has the equation :math:`y=\frac{1}{4}x^2`.  That is, :math:`a = \frac{1}{4}`.  For this parabola, :math:`c=1`.

To derive this result, consider a general point on the parabola, :math:`Q=(x, ax^2)`.  The vertical distance down to the directrix is just 

.. math::

    d_d = ax^2 + c

We'll square this for use below

.. math::

    {d_d}^2 = (ax^2 + c)^2

The other is given by the Pythagorean Theorem

.. math::

    {d_f}^2 = x^2 + (ax^2 - c)^2

Our claim is that these two distances should be equal, so the squares should also be equal

.. math::

    (ax^2 + c)^2 = x^2 + (ax^2 - c)^2
    
    a^2x^4 + 2ax^2c + c^2 = x^2 + a^2x^4 - 2ax^2c + c^2

    2ax^2c = x^2 - 2ax^2c

    4ax^2c = x^2

    4ac = 1

For example, if :math:`a = 1`, :math:`c = \frac{1}{4}`.

Probably the most interesting property of the parabola is that any light ray coming down vertically will bounce off the surface of the parabola so that it is reflected to the focus.  Reflecting telescopes are made in this way.  

The reverse is also true.  The inside of a headlight has a parabolic shape, so that the light coming from a point source is focused into a parallel beam that goes back along the axis of symmetry.

========
Rotation
========

A rotation of the parabola will make life more complicated.  You are probably used to seeing examples where a parabola opens to the right or left.  These are obtained by having an equation like

.. math::

    a(y-k)^2 = (x-h)

with :math:`x = g(y)`.

Then, the easiest thing to do is to switch :math:`x` for :math:`y`, solve the problem, and switch back at the end.

But it is also possible to rotate through a different angle, like :math:`45^\circ`.  What happens then?  Well, basically we replace :math:`x` and :math:`y` by :math:`u` and :math:`v` with

.. math::

    x = u \cos \theta - v \sin \theta

    y = u \sin \theta + v \cos \theta

I derived these here...(need link)

For :math:`45^\circ`, :math:`\sin \theta = \cos \theta = 1/ \sqrt{2}`.

Let

.. math::

    k = \sin \theta = \cos \theta = 1/ \sqrt{2}

Substitute for :math:`x` and :math:`y` as given above

.. math::

    y = ax^2 + bx + c

    ku + kv = a(ku - kv)^2 + b(ku - kv) + c

    u + v = ak(u^2 - 2uv + v^2) + b(u - v) + \frac{c}{k}

Now, we might attempt to solve this for :math:`v` in terms of :math:`u`, but there is a new term :math:`-2uv` which mixes up :math:`u` and :math:`v`.  That is what gives a parabola that is not symmetric with respect to either the :math:`x`-axis or the :math:`y`-axis.

=====
Slope
=====

Using calculus, for a parabola in standard orientation, we can find the slope of the tangent line to the curve at any point by taking the derivative

.. math::

    m = \frac{d}{dx} (ax^2 + bx + c) = 2ax + b

The slope of the tangent is zero at the vertex

.. math::

    m = 2ax + b = 0

    x = -\frac{b}{2a}

as we saw before.

=============
Parallel rays
=============

Above we said that if the light source is placed at the focus of a paraboloid headlight, then rays reflected off the surface emerge "straight out" (or up, as we usually draw parabolas).  Conversely, light rays parallel to the axis of symmetry that enter a paraboloid converge at the focus.

Here is a proof of this that uses vectors.  It is not as clean as I'd like (there is a bit of algebra) but it isn't too bad.  Start with a standard parabola centered with its vertex at the origin with equation :math:`y=ax^2`.  At any point on the parabola :math:`P = (x,ax^2)`, the tangent line to the parabola has slope :math:`2ax`, by the most basic result in calculus.

Draw a vector :math:`\mathbf{u}` from the focus :math:`F = (0,c)` to the point :math:`P`.  This vector has components

.. math::

    \mathbf{u} = \langle x, ax^2 - c \rangle

Draw a vector :math:`\mathbf{v}` extending vertically up from point :math:`P`, its components are

.. math::

    \mathbf{v} = \langle 0, k \rangle

where :math:`k` can be any constant.

Finally, draw the vector :math:`\mathbf{w}` parallel to the tangent line.  :math:`\mathbf{w}` has the same slope as the tangent line, so one version of it could be

.. math::

    \mathbf{w} = \langle 1, 2ax \rangle

The statements above about the paths of light rays can be restated as follows:  the angle :math:`\theta` between :math:`\mathbf{u}` and :math:`\mathbf{w}` is equal to the angle :math:`\phi` between :math:`\mathbf{v}` and :math:`\mathbf{w}`.  We can calculate these angles using the dot product.  Recall that

.. math::

    \mathbf{u} \cdot \mathbf{w} = u w \cos \theta

    \mathbf{v} \cdot \mathbf{w} = v w \cos \phi

So if :math:`\theta = \phi`, then :math:`\cos \theta = \cos \phi` and :math:`w \cos \theta = w \cos \phi` so that

.. math::

    \frac{\mathbf{u} \cdot \mathbf{w}}{u} = \frac{\mathbf{v} \cdot \mathbf{w}}{v}

Conversely, if this equality holds, then :math:`\theta = \phi`.

We calculate these values in the usual way:

.. math::

    \mathbf{u} \cdot \mathbf{w} = x + 2ax (ax^2 - c)

    \mathbf{v} \cdot \mathbf{w} = 2ax k

    u = | \mathbf{u} | = \sqrt{x^2 + (ax^2 - c)^2}

    v = | \mathbf{v} | = k

Our equation is:

.. math::

    \frac{\mathbf{u} \cdot \mathbf{w}}{u} = \frac{\mathbf{v} \cdot \mathbf{w}}{v}

From what we had above, the right-hand side is easy:

.. math::

    \frac{\mathbf{v} \cdot \mathbf{w}}{v} = \frac{2axk}{k} = 2ax

We are reassured to see the arbitrary constant :math:`k` go away.  The left-hand side is a bit of a mess:

.. math::

    \frac{\mathbf{u} \cdot \mathbf{w}}{u}  = \frac{x + 2ax (ax^2 - c)}{\sqrt{x^2 + (ax^2 - c)^2} }

So what we need to do is prove that

.. math::

    \frac{x + 2ax (ax^2 - c)}{\sqrt{x^2 + (ax^2 - c)^2} } = 2ax

    x + 2ax (ax^2 - c) = 2ax \sqrt{x^2 + (ax^2 - c)^2}

We can factor out one :math:`x` right away

.. math::

    1 + 2a (ax^2 - c) = 2a \sqrt{x^2 + (ax^2 - c)^2}

Expand a little bit

.. math::

    1 + 2a^2x^2 - 2ac = 2a \sqrt{x^2 + (ax^2 - c)^2}

And now we just have to do the grunt work of squaring both sides.  The left-hand side is

.. math::

    (1 + 2a^2x^2 - 2ac)^2

    = 1 + 2a^2x^2 - 2ac + 2a^2x^2 + 4a^4x^4 - 4a^3cx^2 - 2ac - 4a^3cx^2 + 4a^2c^2

    = 1 + 4a^2x^2 - 4ac + 4a^4x^4 - 8a^3cx^2 + 4a^2c^2

while the square of the right-hand side is

.. math::

    4a^2 \ [ \ x^2 + (ax^2 - c)^2 \ ]

    = 4a^2(x^2 + a^2x^4 - 2acx^2 + c^2)

    = 4a^2x^2 + 4a^4x^4 - 8a^3cx^2 + 4 a^2c^2

We see that each term on the right-hand side has a matching term on the left-hand side.  All of these can be canceled, leaving 

.. math::

    1 - 4ac = 0

But recall from the section on \textbf{focus and directrix} that :math:`4ac = 1`.  Thus, all the terms cancel, and we have shown that the two sides are equal.  So indeed

.. math::

    \frac{\mathbf{u} \cdot \mathbf{w}}{u} = \frac{\mathbf{v} \cdot \mathbf{w}}{v}

and therefore

.. math::

    w \cos \theta = w \cos \phi

and so

.. math::

    \theta = \phi

===============
Alternate proof
===============


.. image:: /figs/Kline_4_22.png
   :scale: 50 %

Morris Kline has an alternate proof in his book *Calculus*.  In the figure we need to show that angles :math:`1` and :math:`2` are equal.  By standard geometry angles :math:`2` and :math:`3` are equal, hence we need to show that angles :math:`1` and :math:`3` are equal.  We do this by showing that :math:`FP` is equal to :math:`FT`.

Rather than substitute for :math:`y = ax^2` we just leave things in terms of :math:`y`.  Notice that the diagram uses :math:`p` for the distance from the origin to the focus, and labels :math:`P = (x_1,y_1)`.  Using Pythagoras, as indicated, the distance :math:`FP` is 

.. math::

    FP = \sqrt{x_1^2 + (y_1-p)^2}

To get :math:`FT` we need to find what is labeled as :math:`y_2`, the intercept of the tangent line with the :math:`y`-axis.  We get this from the point-slope formula:

.. math::

    \frac{y_1 + y_2}{x_1} = 2ax_1

    y_1 + y_2 = 2ax_1^2

But of course :math:`y_1 = ax_1^2` and so

.. math::

    y_1 + y_2 = 2y_1

Thus :math:`y_1 = y_2` and hence :math:`FT = y_1 + p`.

Going back to :math:`FP`, we use the same crucial fact about the focus that we relied on in the first proof, namely that :math:`4ap = 1` and so

.. math::

    y_1 = ax_1^2

    x_1^2 = 4p y_1

Our previous expression was

.. math::

    FP = \sqrt{x_1^2 + (y_1-p)^2}

substituting for :math:`x_1^2`

.. math::

    FP = \sqrt{4py_1 + (y_1-p)^2}

    = \sqrt{4py_1 + y_1^2 - 2y_1p +  p^2}

    = \sqrt{y_1^2 + 2y_1p +  p^2}

    = \sqrt{(y_1 + p)^2}

    FP = y_1 + p

:math:`FT` and :math:`FP` are the same length, and so the two angles are equal.  Also, we showed that :math:`FP = y + p`, which means that every point on the parabola has the distance :math:`y + p` to the focus, as well as the vertical distance :math:`y + p` to a horizontal line a distance of :math:`p` below the :math:`x`-axis and parallel to it.  This line is the directrix.