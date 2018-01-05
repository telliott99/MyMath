.. _kepler-newton:

#################
Kepler and Newton
#################

This is part one of ten, about deriving Kepler's Laws for planetary motion from Newton's Laws.  In this part, we look at the geometric proof of K2 used by Newton.

.. image:: /figs/newton_area.png
   :scale: 50 %

In the diagram the sun is at :math:`S` and a planet is at :math:`A`.

Consider two small adjacent intervals of time.  In the first, :math:`\Delta t`, the planet travels from :math:`A` to :math:`B` at constant velocity.

In the absence of a force, it would travel to :math:`C` in the next unit of time.  The velocity would be constant and so the length of :math:`AB` is the same as that of :math:`BC`.

Since :math:`ABC` is a straight line and :math:`AB = BC`, the area of :math:`\triangle ABS` is equal to the area of :math:`\triangle BCS`.

Proof:  draw the vertical line (not shown) from :math:`S` to the line containing :math:`ABC`.  The area of either triangle is one-half the length of that altitude times the distance, either :math:`AB` or :math:`BC`.  The principle is illustrated in the next figure.

.. image:: /figs/triangles_parallel.png
   :scale: 50 %

Given two parallel lines separated by a distance :math:`h`, pick two points on one line separated by a distance :math:`d` and *any* point on the other line.  The triangles drawn using those points will all have equal area, namely :math:`(1/2)dh`.

Now, consider the force that will alter the trajectory from :math:`BC` to something else.  We postulate that the force is a "central force", directed *toward the sun*, and that it is applied in small increments (i.e. we do not use calculus).  We have the previous motion along :math:`AB`, the motion that would occur in the absence of a force along :math:`BC`, and we consider the incremental change in the path of the planet.

As a result of application of the force at :math:`B` along the path :math:`EBS`, the trajectory :math:`BC` is modified by the change in velocity resulting from application of the force. The addition is the velocity due to the force times :math:`\Delta t`.  Call that length :math:`CD` and add it by vector addition to :math:`BC` to give the observed trajectory, :math:`BD`.

Now, :math:`CD` is parallel to :math:`SBE` (since the force was actually applied at :math:`B` toward the sun).  Therefore, every point on :math:`CD`, including :math:`D`, has an altitude with respect to :math:`SBE` of the same length.  So we draw a triangle with the base :math:`SB` and third point either :math:`C` or :math:`D` and the two triangles will have equal area.

.. image:: /figs/newton_area.png
   :scale: 50 %

The area of :math:`\triangle BDS` is equal to the area of :math:`\triangle BCS`, which was found earlier to be equal to the area of :math:`\triangle ABS`.  Since the two triangles from the actual motion have the same area, the area is constant.
