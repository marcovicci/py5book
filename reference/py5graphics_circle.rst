Py5Graphics.circle()
====================

Draws a circle to the screen.

Description
-----------

Draws a circle to the screen. By default, the first two parameters set the location of the center, and the third sets the shape's width and height. The origin may be changed with the :doc:`py5graphics_ellipse_mode` function.

This method is the same as :doc:`sketch_circle` but linked to a ``Py5Graphics`` object. To see example code for how it can be used, see :doc:`sketch_circle`.

Underlying Processing method: PGraphics.circle

Signatures
----------

.. code:: python

    circle(
        x: float,  # x-coordinate of the ellipse
        y: float,  # y-coordinate of the ellipse
        extent: float,  # width and height of the ellipse by default
        /,
    ) -> None

Updated on September 01, 2022 14:08:27pm UTC

