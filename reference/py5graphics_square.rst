Py5Graphics.square()
====================

Draws a square to the Py5Graphics drawing surface.

Description
-----------

Draws a square to the Py5Graphics drawing surface. A square is a four-sided shape with every angle at ninety degrees and each side is the same length. By default, the first two parameters set the location of the upper-left corner, the third sets the width and height. The way these parameters are interpreted, however, may be changed with the :doc:`py5graphics_rect_mode` function.

This method is the same as :doc:`sketch_square` but linked to a ``Py5Graphics`` object. To see example code for how it can be used, see :doc:`sketch_square`.

Underlying Processing method: PGraphics.square

Signatures
----------

.. code:: python

    square(
        x: float,  # x-coordinate of the rectangle by default
        y: float,  # y-coordinate of the rectangle by default
        extent: float,  # width and height of the rectangle by default
        /,
    ) -> None

Updated on September 01, 2022 14:08:27pm UTC

