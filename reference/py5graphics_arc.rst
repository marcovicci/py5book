Py5Graphics.arc()
=================

Draws an arc to the screen.

Description
-----------

Draws an arc to the screen. Arcs are drawn along the outer edge of an ellipse defined by the ``a``, ``b``, ``c``, and ``d`` parameters. The origin of the arc's ellipse may be changed with the :doc:`py5graphics_ellipse_mode` function. Use the ``start`` and ``stop`` parameters to specify the angles (in radians) at which to draw the arc. The start/stop values must be in clockwise order.

There are three ways to draw an arc; the rendering technique used is defined by the optional seventh parameter. The three options, depicted in the examples, are ``PIE``, ``OPEN``, and ``CHORD``. The default mode is the ``OPEN`` stroke with a ``PIE`` fill.

In some cases, the ``arc()`` function isn't accurate enough for smooth drawing. For example, the shape may jitter on screen when rotating slowly. If you're having an issue with how arcs are rendered, you'll need to draw the arc yourself with :doc:`py5graphics_begin_shape` & :doc:`py5graphics_end_shape` or a ``Py5Shape``.

This method is the same as :doc:`sketch_arc` but linked to a ``Py5Graphics`` object. To see example code for how it can be used, see :doc:`sketch_arc`.

Underlying Processing method: PGraphics.arc

Signatures
----------

.. code:: python

    arc(
        a: float,  # x-coordinate of the arc's ellipse
        b: float,  # y-coordinate of the arc's ellipse
        c: float,  # width of the arc's ellipse by default
        d: float,  # height of the arc's ellipse by default
        start: float,  # angle to start the arc, specified in radians
        stop: float,  # angle to stop the arc, specified in radians
        /,
    ) -> None

    arc(
        a: float,  # x-coordinate of the arc's ellipse
        b: float,  # y-coordinate of the arc's ellipse
        c: float,  # width of the arc's ellipse by default
        d: float,  # height of the arc's ellipse by default
        start: float,  # angle to start the arc, specified in radians
        stop: float,  # angle to stop the arc, specified in radians
        mode: int,  # arc drawing mode
        /,
    ) -> None

Updated on September 01, 2022 14:08:27pm UTC

