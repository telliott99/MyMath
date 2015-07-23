.. _value-of-pi:

############
Value for Pi
############

This is an explanation of Archimedes' method for finding an approximation to the irrational number :math:`\pi`.  The method uses *inscribed* and *circumscribed* polygons around a circle.  The circle has a diameter equal to :math:`1` and so its circumference is equal to :math:`\pi`.

We will approximate the the value of :math:`\pi` by squeezing it between two other values, the perimeter of the inscribed polygon, which is less than the circumference, and the perimeter of the circumscribed polygon, which is greater than the circumference.

The figure below shows a sketch of the polygons when :math:`n=8`.  We will be increasing the number of sides by a factor of :math:`2` at each step, so these are really :math:`2^n`-gons.  Here, :math:`n=3`.

.. image:: /figs/pi.png
   :scale: 50 %

\subsection*{Finding perimeters in terms of angle :math:`\theta`}

For the left panel, we have :math:`8` sides, so the central angle (marked :math:`2\theta`) is equal to :math:`45^\circ`, and :math:`\theta` is one-half that.  By a standard theorem, the larger triangle with angle :math:`\theta` is a right triangle, so the length of the inscribed n-gon side is :math:`S = sin \ \theta`, since the hypotenuse of the triangle is the diameter of the circle, which is equal to :math:`1`.  The total perimeter is :math:`2^n=8` times S.

For the right panel, we have just rotated the diameter a little bit, it's the same circle, but with n-gons outside, circumscribing the circle.  So the angle marked :math:`\theta` is half the angle we marked as :math:`2 \theta` previously since the diameter comes down to the middle of the side.  It has the same measure as :math:`\theta` from before, and the length of the half-side for that triangle is :math:`(1/2)T` divided by :math:`1/2` (the half diameter) and so equals :math:` tan \ \theta`.  But that means :math:`T = tan \ \theta`.

So all of this gives us two equations, at each stage there are :math:`2^n` sides, the length of each short side :math:`S` on the inside equals :math:`sin \ \theta` and the length of each short side on the outside :math:`T` is equal to :math:`tan \ \theta`.  :math:`S` and :math:`T` are equal to the sine and tangent of the angle :math:`\theta`, where :math:`\theta = 180/2^n`.

=============
The base case
=============

If we go back to the square (:math:`n=2, 2^n = 4`), then the total perimeter of the outside n-gon is equal to :math:`4` times the diameter :math:`= 4 = 4T` (so :math:`T=1`), while the total perimeter of the inside n-gon is equal to :math:`4/ \sqrt{2} = 4S` (so :math:`S = 1/\sqrt{2}`), which is correct.  :math:`\angle \ \theta = 45^\circ` and its tangent is :math:`1` and its sine is :math:`1/\sqrt{2}`.

Now, what we are going to do is to increase :math:`n` in steps of 1, that increases :math:`2^n` by a factor of :math:`2^1 = 2` each time, which halves the angle.  All we need is a way to compute trigonometric functions of :math:`\theta/2`, knowing the values for :math:`\theta`, so we can calculate what happens to the perimeter.

===================
Half angle formulas
===================

We will derive the sum of angles formulas :ref:`elsewhere <cosine_s+t>`.  Let's do cosine first

.. math::

    \cos(x+y) = \cos x \cos y -  \sin x \sin y 

if :math:`x=y` then

.. math::

    \cos \ 2x = \cos^2x - \sin^2x = 2 \cos^2x - 1 

    \cos^2x = \frac{1}{2}(1 + \cos \ 2x) 

    \cos x = \sqrt{\frac{1 + \cos \ 2x}{2}}

And

.. math::

    \sin(x+y) = \sin x \cos y +  \sin y \cos x 

if :math:`x=y` then

.. math::

    \sin \ 2x = 2 \sin x \cos x 

    \sin x = \frac{1}{2} \sin \ 2x  \ \frac{1}{\cos x} =  \frac{1}{2} \sin \ 2x \ \sqrt{\frac{2}{1+\cos\ 2x}}

So if we know :math:`\cos\ 2x` we can use the first formula to get :math:`\cos x` and then apply the second to get :math:`\sin x`.  Finally, divide to get the tangent.

================
Simpler formulas
================

Suppose we know all the values---sine, cosine and tangent---given angle :math:`\theta`---for some value of :math:`n`.  Let us designate them as :math:`S`, :math:`C` and :math:`T`, and we will then substitute :math:`\theta = 2x`.  Using the above formulas, we can calculate :math:`\cos x`, etc.  Let's designate these values for the half-angle as C', S' and T'.

On the web pages that got me started with this derivation

http://personal.bgsu.edu/~carother/pi/Pi3d.html

there is a simpler pair of formulas listed, namely, for an inside perimeter of :math:`p` and an outside perimeter of :math:`P`

.. math::

    P' = \frac{2pP}{p + P} 

    p' = \sqrt{pP'} 

which means that :math:`P'` is the *harmonic mean* of :math:`p` and :math:`P`, while :math:`p'` is the geometric mean of :math:`p` and :math:`P'`.  I thought it would be worthwhile to demonstrate the connection.

I have to admit I puzzled over it for a while, the reason is that I confused these formulas for the perimeters with the formulas we develop below, which are for the sine and tangent of the angle.

======
Onward
======

We have

.. math::

    \sin x = \frac{1}{2} \sin \ 2x  \ \frac{1}{\cos x} 

    S' = \frac{1}{2} \ S \ \frac{1}{C'} 

also

.. math::

    \cos^2x = \frac{1}{2}(1 + \cos \ 2x) 

    (C')^2 = \frac{1}{2}(1+C) = \frac{1+C}{2} 

The first formula from the website is for :math:`T'`

.. math::

    T' = \frac{S'}{C'} = \frac{1}{2} \ S \ \frac{1}{C'} \ \frac{1}{C'} = \frac{1}{2} \ S \ \frac{2}{1+C} =  \frac{S}{1+C}

multiply top and bottom by :math:`T`

.. math::

    T' =  \frac{ST}{S+T}

For the second one

.. math::

    S' = \frac{1}{2} \ S \ \frac{1}{C'} =  \frac{1}{2} \ S \ \frac{T'}{S'} 

    S' = \sqrt{\frac{ST'}{2}}

Let's try checking the results for a known angle

.. math::

    2x = \pi/3, \sin = \frac{\sqrt{3}}{2}, \cos = \frac{1}{2}, \tan = \sqrt{3} 

    x = \pi/6, \sin = \frac{1}{2}, \cos = \frac{\sqrt{3}}{2}, \tan = \frac{1}{\sqrt{3}} 

Our first equation is

.. math::

    T' =  \frac{ST}{S+T} = \frac{3/2}{(3/2)\sqrt{3}} = \frac{1}{\sqrt{3}} 

That looks good.  The second one is

.. math::

    S' = \sqrt{\frac{ST'}{2}} 

    ST' = \frac{\sqrt{3}}{2} \frac{1}{\sqrt{3}} = \frac{1}{2} 

    S' = \sqrt{ \frac{1}{2}\ \ \frac{1}{2}} = \frac{1}{2} 

These both look correct.

==========
Resolution
==========

Just a brief reminder about nomenclature.  We have :math:`P` and :math:`p`, the perimeters of the circumscribed n-gon and the inscribed n-gon.  We have :math:`S` and :math:`T`, for the sine and cosine of the angle (as described above).  And we use a prime :math:`'` to designate the :math:`n+1` version of each of these values, compared with the current version which is the :math:`n` version.  And at each stage we have that

.. math::

    p = 2^n S 

    P = 2^n T 

We also have our equations

.. math::

    T' =  \frac{ST}{S+T} 

    S' = \sqrt{\frac{ST'}{2}} 

and their equations

.. math::

    P' = \frac{2pP}{p + P} 

    p' = \sqrt{pP'} 

and we need to reconcile them.

Start with

.. math::

    P' =  2^{n+1} \ T'= 2^{n+1} \ \frac{ST}{S+T} 

    = 2 \ 2^{n} \ \frac{2^n}{2^n} \ \frac{ST}{S+T} 

    = 2 \frac{2^nS \ 2^n T}{2^n (S + T)}

    = 2 \frac{pP}{p + P}

So, we gain a factor of two, as we needed.  And

.. math::

    (S')^2 = \frac{ST'}{2} 

    (p')^2 = 2^{n+1} \ 2^{n+1} \ (S')^2 = 2 \ 2^n \ 2^{n+1} \frac{ST'}{2} 

    = 2 \frac{2^n S \ 2^{n+1}T'}{2} =  2 p P / 2 = p P' 

    p' = \sqrt{p P'} 

As stated.

Now, I think we should run a simulation to see what kind of numbers we get.  We start with the square (:math:`n=2`, :math:`2^n = 4`)

Previously we found that :math:`S=1/\sqrt{2}` and :math:`T=1` so

.. math::

    p = 2^n S = \frac{4}{\sqrt{2}} = 2.8284 

    P = 2^n T = 4 

Let's try a script to calculate this to larger :math:`n`.

`script.py`:

.. sourcecode:: python

    p = 4.0/(2**0.5)
    P = 4

    def one_round(t):
        p,P = t
        P2 = 2*p*P/(p+P)
        p2 = (p*P2)**0.5
        return p2,P2

    s = '%3.10f  %3.10f'
    print '%2d' % 1, s % (p,P)
    for i in range(18):
        p,P = one_round((p,P))
        if not i%3:
            print '%2d' % (i+2), s % (p,P)

.. sourcecode:: bash

    > python script.py
     1 2.8284271247  4.0000000000
     2 3.0614674589  3.3137084990
     5 3.1403311570  3.1441183852
     8 3.1415729404  3.1416320807
    11 3.1415923456  3.1415932696
    14 3.1415926488  3.1415926632
    17 3.1415926535  3.1415926537
    > 



