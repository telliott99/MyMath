.. _eratosthenes:

############
Eratosthenes
############

Eratosthenes (ca. 276 - 195 BCE)

https://en.wikipedia.org/wiki/Eratosthenes

is famous above all for his "sieve" which allows one to enumerate the prime numbers in an economical fashion, and for measuring the circumference of the earth.

The latter feat derives in the first instance from observation:  at high noon on June 21st there was no shadow  seen at Syene, e.g., allegedly from a stick in the ground.

.. image:: /figs/aswan.png
   :scale: 50 %

Syene is presently known as Aswan.  At 24.1 degrees north latitude, it is close enough to having the sun directly overhead on June 21.  (The "Tropic of Cancer" is at 23 degrees, 26 minutes north).

This news reached Alexandria, a famous center of learning of the ancient world.  Alexandria lies some 500 miles north of Syene, and anyone there could observe that at high noon on June 21st there *was a shadow*, which Eratosthenes measured to be some 7 degrees and a bit (7 degrees and 10 minutes).

.. image:: /figs/eratosthenes.png
   :scale: 50 %

Now, a full 360 degrees divided by 7 degrees and a bit is about 50.  So we can calculate on this basis that the circumference of the earth is about :math:`50 \times 500 = 25000` miles.  That's really close to the correct value.

Can we justify this?  Sure!

We assume that the sun's rays are effectively parallel (not a bad assumption given a distance of 93 million miles).

Then we just use this:

.. image:: /figs/eratosthenes2.png
   :scale: 50 %

and this:

http://hotmath.com/hotmath_help/topics/alternate-interior-angles-theorem.html

angles :math:`\angle 6 \text{ and } \angle 3` are equal.

.. image:: /figs/alternate-angles.png
   :scale: 50 %

Actually, this theorem is not proved by Euclid.  It is a postulate (number 5):

    If a straight line that meets two straight lines makes the interior angles on the same side less than two right angles, then those two straight lines, if extended, will meet on that same side.
    
http://www.themathpage.com/aBookI/first.htm#post
    
So conversely, if two straight lines are parallel and are met by another straight line, the interior angles add up to two right angles or 180 degrees.  Given this, the alternate interior angles theorem follows immediately, and the fact that the angles of a triangle add up to 180 degrees follows shortly after.
