.. _related_rates:

#############
Related rates
#############

One simple form of related rates problem involves two objects moving at right angles from each other, with positions and speeds given in terms of the origin.  For example:

    :math:`A` moves west at :math:`x` miles per hr, his current position is :math:`x_0` miles west of the origin, while :math:`B` moves south at :math:`y` miles per hr, and his current position is :math:`y_0` miles south of the origin.  At what rate are they moving apart?

For the distance, we use Pythagoras:

.. math::

    h^2 = x^2 + y^2

All three values are functions of time so

.. math::

    2h h' = 2 x x' + 2 y y'

    h' = \frac{1}{h} (x x' + y y')

We set :math:`x=x_0` and :math:`y=y_0`, and we will have to calculate :math:`h` from :math:`x_0` and :math:`y_0`.

Another simple related rates problem involves two quantities with an equation relating them, e.g. the volume and radius of a sphere, where the sphere is a "balloon being inflated" or something

.. math::

    V = \frac{4}{3} \pi r^3

    \frac{dV}{dt} = 4 \pi r^2 \ \frac{dr}{dt}

or as usually stated in these problems

.. math::

    V' = 4 \pi r^2 \ r'

If we know :math:`V'` and :math:`r` we can calculate :math:`r'`.  Usually, rather than give you :math:`r` they will give you :math:`V`, so then

.. math::

    r = (\frac{4}{3} V)^{1/3}

A related problem :) is where the object is a cone (maybe inverted) and it's filling up with a fluid.  

.. image:: /figs/cone_rates.png
   :scale: 50 %

Here, the formula for the volume of a cone is

.. math::

    V = \frac{1}{3} \pi r^2 h

The problem is that since :math:`r` and :math:`h` depend on each other, we can't simply do 

.. math::

    V' = \frac{1}{3} \pi r^2 h'
    
(this is wrong!)

In this case it's important to realize that the radius :math:`r` and the height :math:`h` of the fluid at its current level have the same ratio as the radius :math:`R` and height :math:`H` of the container.

.. math::

    \frac{r}{h} = \frac{R}{H}

    r = \frac{R}{H} h

    h = \frac{H}{R} r

so we can substitute using the relationship between :math:`r` and :math:`h`

.. math::

    V = \frac{1}{3} \pi r^2 \frac{H}{R} r = \frac{1}{3} \pi \frac{H}{R} r^3

Alternatively, we can eliminate :math:`r`

.. math::

    V = \frac{1}{3} \pi \frac{R^2}{H^2} h^3

For example, with the figure above, (:math:`R=5` and :math:`H=14` feet), and given water is draining from the tank at :math:`V'=-2 ft^3` per hour

    "At what rate is the depth of the water in the tank changing when the depth of the water is :math:`6` ft?"

.. math::

    V = \frac{1}{3} \pi \frac{R^2}{H^2} h^3

    V' = \pi \frac{R^2}{H^2} h^2 h'

We're given :math:`V'` and :math:`h`, :math:`H` and :math:`R`, and so can solve for :math:`h'`.

The second question is 

    "At what rate is the radius of the top of the water in the tank changing when the depth of the water is 6 ft?"

We need :math:`r'` given :math:`h` (and :math:`R`, :math:`H`, and :math:`V'`)

.. math::

    V = \frac{1}{3} \pi \frac{H}{R} r^3

    V' = \pi \frac{H}{R} r^2 r'

    r = \frac{R}{H} h

    r^2 = (\frac{R}{H})^2 h^2

Plugging in

.. math::

    V' = \pi \frac{R}{H} h^2 r'

Here is another related rates problem.  An airplane and a parachutist are at the same height currently, and in the same direction as you look at them.  

.. image:: /figs/rr1.png
   :scale: 50 %

The airplane moves away from you at :math:`500` ft/s.  The parachutist is floating downward at :math:`-10` ft/s and will land :math:`1000` ft away from you.  The current value of :math:`h = 2000` ft.  The current value of :math:`p = 8000` ft.  Find :math:`d \theta/dt`.

.. math::

    p(t) = p_0 + 500 t

    h(t) = h_0 - 10 t

    p' = 500

    h' = -10

Find equations for the angles involved

.. math::

    \tan s = \frac{2000}{p}

we use the constant value of :math:`2000` rather than :math:`h`, which will vary.

.. math::

    u = s + \theta

    \tan u = \frac{h}{1000}

Take the derivatives.  For the airplane

.. math::

    \tan s = \frac{2000}{p}

    \frac{d}{dt} \tan s = \sec^2 s \frac{ds}{dt} 
    
    = \frac{d}{dt} \frac{2000}{p}  
    
    = -2000 \frac{1}{p^2} \frac{dp}{dt}
    
and

.. math::

    \frac{ds}{dt} = -2000 \frac{1}{p^2} \frac{dp}{dt} \cos^2 s

In the above equation, we know :math:`p=8000` and :math:`dp/dt = 500`.  We have to find the cosine.  If :math:`\tan s=1/4` then :math:`\cos s = \sqrt{16/17}`. 

.. math::
 
    \frac{ds}{dt} = -2000 \ \frac{1}{8000^2} \ 500 \ \frac{16}{17}

    \frac{ds}{dt} = -\frac{1}{4} \frac{1}{16} \frac{16}{17} 
    
    = -\frac{1}{68} = - 0.0147

For the parachutist

.. math::

    \frac{d}{dt} \tan u = \sec^2 u \frac{du}{dt} 
    
    = \frac{d}{dt} \frac{h}{1000}  
    
    = \frac{1}{1000} \frac{dh}{dt}

    \frac{du}{dt} = \frac{1}{1000} \frac{dh}{dt}  cos^2 u

In the above equation, we know :math:`dh/dt = -10`.  We have to find the cosine.  If :math:`\tan u=2` then :math:`\cos u = 1/\sqrt{5}`.  So

.. math::

    \frac{du}{dt} = 0.001 \  (-10) \ \frac{1}{5}  
    
    = - 0.002

Since :math:`\theta = u - s`

.. math::

    \frac{d \theta}{dt} = \frac{du}{dt} -  \frac{ds}{dt} 
    
    = - 0.002 + 0.0147 =  0.0127

The angle :math:`\theta` between plane and parachutist is *increasing* with time (about :math:`3/4` of a degree per second).