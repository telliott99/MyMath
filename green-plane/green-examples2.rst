.. _2D-curl-example:

#############
Curl examples
#############

Green's Theorem is

.. math::

    \oint_C \mathbf{F} \cdot \mathbf{dr} = \iint\limits_{R}  curl(\mathbf{F}) \ dA
    
The left-hand side can be written as:

.. math::

    = \oint_C M \ dx + N \ dy

and the right-hand side is really just:

.. math::

    = \iint\limits_{R} (N_x - M_y) \ dA 

The theorem can be used for finding area by computing a line integral.  The trick is to imagine an :math:`M` and :math:`N` such that

.. math::

    N_x - M_y = 1 

because then we have

.. math::

    \oint_C M \ dx + N \ dy  = \iint\limits_{R}  \ dA = Area 

An especially common choice is:

.. math::

    M = -\frac{y}{2}, \ \ N = \frac{x}{2} 

So we have that

.. math::

    A = \frac{1}{2} \oint_C x \ dy - y \ dx 

Let's try this out on a circle.  What is the parametrization of :math:`C`?  We need :math:`x` and :math:`y` as functions of :math:`t`:

.. math::

    x = a \ cos \ t 

    dx = -a \ sin \ t  \ dt 

    y = a \ sin \ t 

    dy = a \ cos \ t  \ dt 

    A = \frac{1}{2} \int_{t=0}^{t=2\pi} a^2 cos^2t \ dt + a^2 sin^2t \ dt 

    = \frac{1}{2} \ a^2 \ 2 \pi = \pi a^2 

What about an ellipse?  What is the parametrization of :math:`C`?  We need :math:`x` and :math:`y` as functions of :math:`t`:

.. math::

    x = a \ cos \ t, 

    dx = -a \ sin \ t  \ dt 

    y = b \ sin \ t 

    dy = b \ cos \ t  \ dt 

To see that the above is correct, do this

.. math::

    \frac{x^2}{a^2} + \frac{y^2}{b^2} = cos^2 \ t + sin^2 \ t = 1 

Clearly the formula of an ellipse.  Now plug into the integral

.. math::

    A = \frac{1}{2} \int_{t=0}^{t=2\pi} ab \ cos^2t \ dt + ab \ sin^2t \ dt 

    \frac{1}{2} \ ab \ 2 \pi = \pi ab 

Finally, what seems a very simple example:

the part of the rectangle :math:`[0,1] \times [0,2]` below the line :math:`y=2x`,

is actually complicated because there are three segments of the curve:

.. math::

    y = 2x 

    dy = 2 \ dx 

    A = \frac{1}{2} \oint_C x \ dy - y \ dx  

    C1:  x = 0 \to 1,\  y = 0 

    C2:  x = 1,\  y = 0 \to 2 

    C3:  y = 2x,\  x = 1 \to 0 

    M = -\frac{y}{2}, \ \ N = \frac{x}{2} 

    A_1 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C x \ 0 - 0 \ dx = 0  

    A_2 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C 1 \ dy - y \ 0 = y \bigg |_0^2 = 1  

    A_3 = \frac{1}{2} \oint_C x \ dy - y \ dx = \frac{1}{2} \oint_C x \ 2 \ dx - 2x \ dx = 0  

The total area is just 1.

+++++++
Marsden
+++++++

Two more examples are from Marsden.

For the first, the region is the area in the first quadrant lying between :math:`y=x` and :math:`y=x^2` (from :math:`(0,0) \rightarrow (1,1)`).  The field is :math:`\mathbf{F} = \langle xy^2, y+x \rangle`.

Green's Theorem for work is:

.. math::

    \oint_C M \ dx + N \ dy = \iint\limits_{R} (N_x - M_y) \ dA

Do the right-hand side first.  We have

.. math::

    \iint\limits_{R} (N_x - M_y) \ dA = \iint 1 - 2xy \ dy \ dx

The inner integral is

.. math::

    \int_{x^2}^x 1 - 2xy \ dy
    
    = y - xy^2 \ \bigg |_{x^2}^x

    = x - x^3 - x^2 + x^5

The outer integral is

.. math::

    \int_0^1 x - x^3 - x^2 + x^5 \ dx = \frac{x^2}{2} - \frac{x^4}{4} - \frac{x^3}{3} + \frac{x^6}{6} \ \bigg |_0^1
    
    = \frac{1}{2} - \frac{1}{4} - \frac{1}{3} + \frac{1}{6} = \frac{1}{12}

The path integral is

.. math::

    \int_C M \ dx + N \ dy = \int_C xy^2 \ dx + (x + y) \ dy
    
We have two parts to the curve and two different parametrizations.  The lower one is:

.. math::

    x = t \ \ \ t = 0 \rightarrow 1
    
    dx = dt
    
    y = t^2
    
    dy = 2 t \ dt
    
so the integral is

.. math::

    \int xy^2 \ dx + (x + y) \ dy
    
    = \int t^5 \ dt + \int (t + t^2) \ 2t \ dt
    
    = \int_0^1 t^5 + 2t^2 + 2t^3 \ dt
    
    = \frac{1}{6} + \frac{2}{3} + \frac{1}{2} = \frac{8}{6}

(Backward) the upper curve is 

.. math::

    x = t \ \ \ t = 0 \rightarrow 1
    
    y = t
    
    dx = dy = dt
    
so the integral is

.. math::

    \int_0^1 t^3 + 2t \ dt = \int_0^1 t^3 + 2t \ dt
    
    = \frac{1}{4} + 1 = \frac{5}{4}

Putting them together we obtain (remembering to subtract the second path):

.. math::

    \frac{8}{6} - \frac{5}{4} = \frac{16}{12} - \frac{15}{12} = \frac{1}{12}

+++++++
Example
+++++++

.. math::

    \mathbf{F} = \langle 2x^3 - y^3, x^3 + y^3 \rangle
    
This looks unnecessarily complex, but if you compute the curl you will see where we are headed.  We do the line integral first:

.. math::

    \int M \ dx + N \ dy
    
    = \int 2x^3 - y^3 \ dx + x^3 + y^3  \ dy

Our curve is just the unit circle.  So the parametrization is

.. math::

    x = \cos t
    
    y = \sin t
    
    dx = - \sin t \ dt
    
    dy = \cos t \ dt
    
The integral is:

.. math::

    \int 2x^3 - y^3 \ dx + x^3 + y^3  \ dy
    
    = \int 2 \cos^3 t (-\sin t) \ dt + \int \sin^4 t \ dt + \int \cos^4 t \ dt + \int \sin^3 t \cos t \ dt
    
The first and fourth terms are easy.  I re-combine them to give:

.. math::

    \frac{\cos^4 t}{2} + \frac{\sin^4 t}{4} \ \bigg |_0^{2 \pi} = \frac{1}{2} + 0 - \frac{1}{2} - 0 = 0

The rest is:

.. math::

    \int \sin^4 t \ dt + \int \cos^4 t \ dt

Referring back to my cheat sheet (:ref:`here <cos^n>`):

.. math::

    \int \cos^4 t \ dt = \frac{1}{4} \sin t \cos^3 t + \frac{3}{8} (t + \sin t \cos t)
    
    \int \sin^4 t \ dt = -\frac{1}{4} \sin^3 t \cos t + \frac{3}{8} (t -\sin t \cos t)

All the mixed terms go away at any integer multiple of :math:`\pi/2` so we just have:

.. math::

    \frac{3}{4} t \ \bigg |_0^{2 \pi} = \frac{3 \pi}{2}

Doing it the other way:

.. math::

    \mathbf{F} = \langle 2x^3 - y^3, x^3 + y^3 \rangle

    N_x = 3x^2
    
    M_y = -3y^2
    
The area integral is:

.. math::

    \iint\limits_{R} (N_x - M_y) \ dA 
    
    = 3 \iint x^2 + y^2 \ dy \ dx

    = 3 \iint r^2 \ r \ dr \ d \theta
    
    = 3 \ 2 \pi \ \frac{r^4}{4} \ \bigg |_0^1 = \frac{3 \pi}{2}


   