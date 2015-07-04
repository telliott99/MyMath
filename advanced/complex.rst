.. _complex:

###############
Complex Numbers
###############

An example of a *purely* imaginary number is something like :math:`\sqrt{-4}`, which we cannot really work with using only the real numbers.  However, if :math:`i = \sqrt{-1}` by definition, then

.. math::

    \sqrt{-4} = \sqrt{4(-1)} = 2i

It's worth pointing out that even if we can't understand :math:`\sqrt{-4}`, we can still *compute* with it (see the write-up on :ref:`cubic roots <cubics>`).

For example, consider the equation

.. math::

    x^2 + 1 = 0

    x = \sqrt{-1} = i

Note that we could just as well say that :math:`-i` is our solution.  So we should write

.. math::

    x = \pm i

Our two solutions have the property that they are complex conjugates of each other (see below).

A complex number is some combination of a real part plus a imaginary part, in the general form :math:`a + bi`.  Then, addition and subtraction are defined as you would expect:

.. math::

    z_1 \pm z_2 = (a + bi) \pm (c + di)

    = (a \pm c) + (b \pm d)i

Simple enough.  Real combines with real, and imaginary with imaginary.  

It is worth pointing out something powerful here:  if two complex numbers are equal, then *both* the real and the imaginary parts are equal.  This is really useful.

Multiplication also works as you'd expect:

.. math::

    z_1 \times z_2 = (a + bi) \times (c + di)

    = (ac + bdi^2) + (ad + bc)i

    = (ac - bd) + (ad + bc)i

The complex conjugate for a given :math:`z = a + bi` is

.. math::

    z^* = a - bi

and it has the following property, that when we do :math:`z z^*`

.. math::

    (a + bi) \times (a - bi) = ac + bd

The result is a purely real number.  So if you want the real part of a complex number, multiply by its conjugate and take the square root.

========
Division
========

We will see two ways of doing division (and multiplication).  The first way uses the complex conjugate.  Make the denominator purely real by multiplying top and bottom by the complex conjugate of the denominator

.. math::

    \frac{(a + bi)}{(c + di)} \ \frac{(c - di)}{(c - di)} = \frac{(a + bi)(c - di)}{c^2 + d^2}

    =  \frac{1}{c^2 + d^2} \ [ \ (ac + bd) + (bc-ad)i \ ]

==================
Radial coordinates
==================

Instead of :math:`x,y` ccordinates, a different way to represent complex numbers uses the notion of an angle :math:`\theta` and radius :math:`r` in the complex plane.  This idea has in the past been credited to a guy named Argand (the Argand plane).  However, another mathematician named Wessel wrote about it earlier, but his paper was apparently not noticed.

.. math::

    a + bi = r \cos \theta + r i \sin \theta

We use Euler's famous identity

.. math::

    e^{i\theta} = \cos \theta + i \sin \theta

    a + bi = r e^{i\theta}

The :math:`x`-coordinate is :math:`a` and the :math:`y`-coordinate is :math:`b` and so the length of the hypotenuse is 

.. math::

    r = \sqrt{x^2 + y^2}

Compute :math:`\theta` by finding the angle whose tangent is what we need:

.. math::

    \theta = tan^{-1} (\frac{y}{x})

============
Computations
============

With polar coordinates, to multiply two numbers together we multiply their respective :math:`r` values and *add* the angles.

.. math::

    z_1 z_2 = r_1 r_2 e^{i(\theta_1 + \theta_2)}

.. image:: /figs/complex-mult.png
   :scale: 50 %

Conversely, for division, we divide the :math:`r` values and subtract the angles.

.. math::

    \frac{z_1}{z_2} =\frac{r_1}{r_2} e^{i(\theta_1 - \theta_2)}

If it's necessary to convert back from the :math:`r`, :math:`\theta` form to :math:`x,y` coordinates use the fact that

.. math::

    x = r \  cos \theta

    y = r \  i \sin \theta

We gain some feeling for what :math:`\theta` means in the symbol :math:`e^{i\theta}`.  :math:`\theta` is the angle a vector from the origin to the complex number makes with the positive x-axis.

==========
Identities
==========

Because

.. math::

    i^2 = -1

it follows that 

.. math::

    i = -\frac{1}{i}

=====================
More on the conjugate
=====================

It's worth pointing out that the complex conjugate is almost exactly the same point, but reflected across the :math:`x` axis.

.. math::

    z = a + bi = r e^{i\theta}

    z^* = a - bi = r e^{-i\theta}

    z z^* = a^2 + b^2 = r^2 e^{i(\theta + - \theta)} = r^2

The complex conjugate is also written as :math:`\overline{z}`.  Another formula for :math:`r$ i`

.. math::

    r = \sqrt{z z^*}

A useful fact about the conjugate is that, for a more involved expression, we should reverse the sign of each imaginary component.  An example is

.. math::

    z = f + ig

where :math:`f` and :math:`g` are themselves complex, then

.. math::

    z^* = f^* - ig^*

+++++++
Example
+++++++

Let's work an example

.. math::

    \frac{1+i}{1-i} = \ ?

    \frac{1+i}{1-i} \ \frac{1+i}{1+i} = \frac{1 + 2i - 1}{1 + 1}

    = \frac{2i}{2} = i

The other way (with :math:`r`, :math:`\theta`) is

.. math::

    1 + i = \sqrt{2}e^{i \pi/4}

    1 - i = \sqrt{2}e^{i -\pi/4}

    \frac{1+i}{1-i} = \frac{\sqrt{2}}{\sqrt{2}} e^{i \pi/2} = e^{i \pi/2} = i

since :math:`x = r \cos \theta` and :math:`y = r i \sin \theta`.

=====================
Matrix representation
=====================

For the math wonks, a complex number is really just an *ordered pair* of real numbers :math:`(a,b)`.  Another representation is as a matrix

.. math::

    z_1 = a + bi = 
    \begin{bmatrix}
    a & -b \\
    b & \ \ a
    \end{bmatrix}

    z_2 = c + di = 
    \begin{bmatrix}
    c & -d \\
    d & \ \ c
    \end{bmatrix}

Then :math:`z_1 + z_2` and :math:`z_1 \times z_2 = z_1z_2` work as expected

.. math::

    z_1 z_2 = (ac - bd) + (ad + bc) i

    z_1 z_2 =
    \begin{bmatrix}
    a & -b \\
    b & \ \ a
    \end{bmatrix} 
    \begin{bmatrix}
    c & -d \\
    d & \ \ c
    \end{bmatrix}
    = 
    \begin{bmatrix}
    ac - bd & -ad - bc \\
    cb + ad & \ \ ac - bd
    \end{bmatrix} 

and the real part of :math:`z` (the length :math:`r`), squared, is the determinant

.. math::
 
    |z|^2 =
    \begin{vmatrix}
    a & -b \\
    b & \ \ a
    \end{vmatrix}
    = a^2 + b^2

==========
Logarithms
==========

Write 

.. math::

    z = e^w

    w = \ln z

We wish to have

.. math::

    \ln z_1 z_2 = \ln z_1 + \ln z_2

    w = \ln z = \ln (re^{i\theta})

    = \text{Ln}\ r + \ln e^{i\theta}

So

.. math::

    w = \ln z = \text{Ln}\ r + i\theta

where :math:`\text{Ln}\ r` is the ordinary real logarithm.
