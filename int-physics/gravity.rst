.. _gravity:

#######
Gravity
#######

The simplest kind of motion is movement in a single dimension.  To analyze it, the first thing we need to do is to pick an origin for our coordinate system, the place where :math:`x` or :math:`y=0`.  For a gravity problem the only dimension is up and down, and usually it's most convenient to pick the ground as the origin.  

Next, we need to decide when to start the clock, to say when is :math:`t=0`.

Then, in physics such problems often have constant acceleration due to gravity, with :math:`\mathbf{a}=-9.8` m/sec\ :math:`^2`.  For simplicity we can take :math:`\mathbf{a}=-10` m/sec\ :math:`^2`.  The minus sign indicates that our coordinate system assigns positive numbers to positions further above us than ground-level, while the acceleration due to gravity points toward the earth.  In one dimension, we need not worry about vectors and direction, we just have to remember the convention about sign.

Velocity is the derivative of position with respect to time.

.. math::

    v = \frac{dx}{dt}

(in one dimension, velocity is the same as speed, in more than one dimension, velocity is a vector).

Acceleration is the second derivative

.. math::

    a = \frac{d^2x}{dt^2} = \frac{dv}{dt}

The two pieces of information with which we usually start the analysis are the initial position :math:`x_0` and the initial velocity :math:`v_0`.  We seek an equation that will tell us the current position, :math:`x(t)`, given these two values plus the acceleration.  Rather than do a formal integration, we make a a guess based on the relationship to the second derivative above:

.. math::

    x(t) \approx at^2 + C

We need to adjust the guess to get rid of the :math:`2` that will come down when we take the first derivative.

.. math::

    x(t) = \frac{1}{2}at^2 + C

We also realize that the constant :math:`C` can include two terms of two types.  First, anything like :math:`t` times something will go away when we take the second derivative, so we should write

.. math::

    x(t) = \frac{1}{2}at^2 + C_1t + C_2

(where :math:`C_1` and :math:`C_2` are now different constants of integration).  If we take the first derivative we have

.. math::

    v(t) = \frac{dx}{dt} = at + C_1

and we recognize that :math:`C_1` is just the initial velocity

.. math::

    v(0) = v_0 = 0 + C_1

so we have

.. math::

    x(t) = \frac{1}{2}at^2 + v_0t + C_2

Finally, we realize that, for :math:`t=0` we have

.. math::

    x(0) = 0 + 0 + C_2 = x_0

so, finally

.. math::

    x(t) = \frac{1}{2}at^2 + v_0t + x_0

.. math::

which should be very familiar.  With this equation in hand, knowing :math:`a`, :math:`v_0` and :math:`x_0`, we have only two variables, :math:`x` and :math:`t`.  Given :math:`t` it is easy to solve for :math:`x`.  Similarly, we can solve for :math:`v` given :math:`t` using

.. math::

    v(t) = at + v_0

It can be a little awkward to find :math:`t` corresponding to a given :math:`x`, but the last equation provides a nice trick for this.  Solve for :math:`t` (simplify the notation by using :math:`v(t) = v`):

.. math::

    v-v_0 = at

    t = \frac{v - v_0}{a}

Now, given :math:`v` (for example :math:`v=0` at the top of the curve) we can find :math:`t`.  We can also plug this into the other equation and get something simple and useful

.. math::

    x(t) = x = \frac{1}{2}at^2 + v_0t + x_0

    x - x_0 = \frac{1}{2}a(\frac{v - v_0}{a})^2 + 2v_0(\frac{v - v_0}{a})

    2a(x - x_0) = (v-v_0)^2 + 2v_0(v - v_0)

    = v^2 - 2v v_0 + v_0^2 + 2v_0 v - 2v_0^2

    = v^2  - v_0^2

So finally

.. math::

    v^2 = v_0^2 + 2a(x - x_0)

Or maybe you prefer

.. math::

    \frac{v^2 - v_0^2}{x - x_0} = 2a
    
Rather than find the time first and plug into the standard equation to get the velocity, we can then go directly between velocity and position or vice versa.

Here are our equations re-written for gravity problems:

.. math::

    y(t) = -\frac{1}{2}gt^2 + v_0t + y_0

    v - v_0 = -gt

    v^2 = v_0^2 - 2g(y - y_0)

================
General examples
================

One simple question is:  what is the time to fall from a given height :math:`h`.  The initial velocity is zero, so

.. math::

    y(t) = -\frac{1}{2}gt^2 + v_0t + y_0

    y - y_0 = 0 - h = -h = -\frac{1}{2}gt^2

    t = \sqrt{\frac{2h}{g}}

And given this time, the terminal velocity is:

.. math::

    v = v_0 - gt = 0 - g \sqrt{\frac{2h}{g}} = -\sqrt{2gh}

The second simple situation is to fire a projectile up with initial velocity :math:`u`.  Then we ask, what is the maximum height.  This is one way

.. math::

    v^2 = v_0^2 - 2g(y - y_0)

    0 = u^2 - 2gh

    h = \frac{u^2}{2g}

Another way is to first get the time:

.. math::

    v - v_0 = -gt

    - u = -gt

    t = \frac{u}{g}

Now the height is

.. math::

    y(t) = -\frac{1}{2}gt^2 + v_0t + y_0

    h = -\frac{1}{2}g(\frac{u}{g})^2 + u\frac{u}{g}

    h = \frac{u^2}{2g}

When the object returns to earth the height is equal to zero

.. math::

    0 = -\frac{1}{2}gt^2 + ut

    u = \frac{1}{2}gt

    t = \frac{2u}{g}

One-half the time is spent going up, and the other half coming down.  It's worth pointing out that the change in potential energy at height :math:`h` is equal to 

.. math::

    U = mgh = mg \frac{u^2}{2g} = \frac{1}{2} m u^2

which is equal to the kinetic energy at launch.

=================
Clever derivation
=================

Dr. Shankar offers this derivation in his first Physics lecture.  Write

.. math::

    \frac{dv}{dt} = a

Multiply both sides by :math:`v`

.. math::

    v \frac{dv}{dt} = av

The first key step is to recognize that the left-hand side is equal (by the chain rule) to 

.. math::

    v \frac{dv}{dt} = \frac{d}{dt} (\frac{v^2}{2})

.. math::

So rewrite what we had including this and on the right-hand side use the definition :math:`v = dx/dt`

.. math::

    \frac{d}{dt} (\frac{v^2}{2}) = a \ \frac{dx}{dt}

The second key is to recognize that we can get rid of :math:`dt` and just think about this as an equality between differentials

.. math::

    d(\frac{v^2}{2}) = a \ dx

Now integrate

.. math::

    \int d(\frac{v^2}{2}) = \int a \ dx

for the constants of integration use the initial values

.. math::

    \frac{v^2}{2} - \frac{v_0^2}{2} = a (x - x_0)

That should look familiar:

.. math::

    v^2 = v_0^2 + 2a (x - x_0)

+++++++
Example
+++++++

Suppose you are on the roof of a building of height :math:`y_0=15` m and throw a rock upward with velocity :math:`v_0=10` m/s.  We find the maximum height as the position where :math:`v=0`.  From the second equation

.. math::

    t = \frac{v-v_0}{a} = \frac{0 - 10}{-10} = 1 \ \text{s}

    y = \frac{1}{2}at^2 + v_0t + y_0 =  (-5) t^2 + (10) t + 15 = 20 \ \text{m}

How fast is it going when it hits the ground?  From the third equation

.. math::

    v^2 = v_0^2 + 2a(y - y_0) = (10)^2 + 2(-10)(-15) = 400

    v = \sqrt{v^2} = \sqrt{400} = \pm \ 20 \ \text{m/s}

There are two solutions, the one with negative value corresponds to the rock hitting the ground at the end of the throw.  The positive velocity is the same rock being thrown from the ground upward with velocity :math:`20` m/s.  This will also hit the ground with velocity :math:`-20` m/s.  

To find the time when the rock hits the ground, from the first equation

.. math::

    y(t) = \frac{1}{2}at^2 + v_0t + y_0 = 0 = (-5)t^2 + 10t + 15

    t^2 - 2t - 3 = 0 = (t-3)(t+1) = 0

So either :math:`t = 3` or :math:`t = -1` seconds.  The first solution is the one we thought we wanted, the second corresponds to the positive velocity situation we had above.  For a throw from the ground up, the trajectory is symmetric, two seconds going up and two seconds coming back down again.  And reusing the second equation, for the part coming down :math:`v - v_0 = at`, so  :math:`v = at = -20` m/s.

======
Part 2
======

This is a simple explanation of how to treat motion near the earth's surface, where the acceleration due to gravity is a constant, :math:`g`.  The velocity of an object in the vertical direction is 

.. math::

    v = v_0 - gt

That is, up is taken to be positive and down is negative.  If an object starts out with velocity :math:`v _0` (in the y-direction), after time :math:`t` its velocity will be given by this equation.  This can be checked by taking the derivative

.. math::

    \frac{d}{dt} \ v = \frac{dv}{dt} = -g

The derivative of velocity with respect to time is acceleration, so this checks.  Here, it is just :math:`-g`.
Similarly distance is also a function of time.  That function is

.. math::

    h = h_0 + v_0 t - \frac{1}{2}gt^2

This expression can be checked by differentiating.  

.. math::

    \frac{d}{dt} \ h = \frac{dh}{dt} = v = v_0 - gt

The result of taking the derivative explains why the distance equation has :math:`-\frac{1}{2}gt^2` while the velocity equation has just :math:`-gt`.

+++++++
Example
+++++++

A ball is thrown so that it goes upward with a velocity of :math:`16 \ m/s`.  If :math:`g = 32 \ ft/s^2`, what is the position of the ball at time :math:`t`?

We have the distance equation

.. math::

    h = h_0 + v_0 t - \frac{1}{2}gt^2

We set $h_0 = 0$, $v_0 = 16$ and $g = 32$

.. math::

    h = 16 t - 16t^2

We wish to know when :math:`h=0`

.. math::

    0 = 16 t (1-t)

:math:`t=0` is a solution, which is obviously correct.  The ball starts with :math:`h=0` at :math:`t=0`.  The other solution is :math:`t=1`.  The ball returns to :math:`h=0` at :math:`t=1`.

Notice also that 

.. math::

    v = v_0 - gt = 16 -32t

so when :math:`v=0`

.. math::

    0 = v_0 - gt = 16 -32t

    16 = 32t

and :math:`t=1/2`.  The trajectory of this ball is a parabola.  It reaches its vertex when the upward velocity is zero (:math:`t=1/2 s`).  It returns to the earth in a time equal to that which was needed for its ascent.

+++++++
Example
+++++++

Find t if a ball is dropped from a height = 392 feet, for :math:`h_0 = 392` and :math:`v_0 = 0`.

The distance equation is

.. math::

    h = h_0 + v_0 t - \frac{1}{2}gt^2

We have :math:`h_0 = 392` and :math:`v_0 = 0`

.. math::

    0 = 392 - \frac{1}{2}gt^2

    784 = 16t^2

    \frac{784}{16} = 49 = t^2

    t =7

+++++++
Example
+++++++

A ball is thrown up in the air making an angle :math:`\theta` with respect to the horizontal.  What value of :math:`\theta` will give the maximum horizontal distance?

.. math::

    x(t) = v_x t

    y(t) = v_y t - \frac{1}{2} g t^2

    v_x = v \cos \theta

    v_y = v \sin \theta

We find the time :math:`t` when :math:`y=0` and the ball has come back down to earth.  We can remove one factor of :math:`t` from each term on the right (we lose a possible solution but it is the one we already know, :math:`y=0` at :math:`t=0`).

.. math::

    y(t) = 0 = v_y t - \frac{1}{2} g t^2

    0 = v_y  - \frac{1}{2} g t

    t = \frac{2}{g} v_y

Substitute for :math:`t` in the equation for :math:`x(t)` above, converting it to :math:`x(\theta)`

.. math::

    x(t) = v_x t = v_x \frac{2}{g} v_y

    x(\theta) = v \cos \theta \ (\frac{2}{g}) \ v \sin \theta

    = \ \frac{2v^2}{g}  \sin \theta \cos \theta

Remembering the sum of angles formula (:math:`\sin 2s = 2 \sin s \cos s`):

.. math::

    = \ \frac{v^2}{g}  \sin 2 \theta

This is a maximum (for fixed :math:`v`) when :math:`\sin 2 \theta` is a maximum (equal to :math:`1`, so :math:`\theta = \pi/4`.

Alternatively

.. math::

    \frac{dx}{d\theta } = 0 = \frac{d}{dx} (\frac{2v^2}{g}) \sin \theta \cos \theta

    0 = (\frac{2v^2}{g}) \ [\ - \sin^2 \theta + \cos^2 \theta \ ]

Eliminate the constants in front and then we have

.. math::

    0 = - \sin^2 \theta + \cos^2 \theta

    \sin \theta = \cos \theta

    \theta = \tan^{-1} 1 = \frac{\pi}{4} = 45^\circ
