Py5Graphics.directional_light()
===============================

Adds a directional light.

Description
-----------

Adds a directional light. Directional light comes from one direction: it is stronger when hitting a surface squarely, and weaker if it hits at a gentle angle. After hitting a surface, directional light scatters in all directions. Lights need to be included in the ``draw()`` to remain persistent in a looping program. Placing them in the ``setup()`` of a looping program will cause them to only have an effect the first time through the loop. The ``v1``, ``v2``, and ``v3`` parameters are interpreted as either ``RGB`` or ``HSB`` values, depending on the current color mode. The ``nx``, ``ny``, and ``nz`` parameters specify the direction the light is facing. For example, setting ``ny`` to -1 will cause the geometry to be lit from below (since the light would be facing directly upward).

This method is the same as :doc:`sketch_directional_light` but linked to a ``Py5Graphics`` object. To see example code for how it can be used, see :doc:`sketch_directional_light`.

Underlying Processing method: PGraphics.directionalLight

Signatures
----------

.. code:: python

    directional_light(
        v1: float,  # red or hue value (depending on current color mode)
        v2: float,  # green or saturation value (depending on current color mode)
        v3: float,  # blue or brightness value (depending on current color mode)
        nx: float,  # direction along the x-axis
        ny: float,  # direction along the y-axis
        nz: float,  # direction along the z-axis
        /,
    ) -> None

Updated on September 01, 2022 14:08:27pm UTC

