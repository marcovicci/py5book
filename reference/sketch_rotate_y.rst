rotate_y()
==========

Rotates around the y-axis the amount specified by the ``angle`` parameter.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_rotate_y_0.png
    :alt: example picture for rotate_y()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(100, 100, py5.P3D)
        py5.translate(py5.width//2, py5.height//2)
        py5.rotate_y(py5.PI/3.0)
        py5.rect(-26, -26, 52, 52)

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_rotate_y_1.png
    :alt: example picture for rotate_y()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(100, 100, py5.P3D)
        py5.translate(py5.width//2, py5.height//2)
        py5.rotate_y(py5.radians(60))
        py5.rect(-26, -26, 52, 52)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Rotates around the y-axis the amount specified by the ``angle`` parameter. Angles should be specified in radians (values from ``0`` to ``TWO_PI``) or converted from degrees to radians with the :doc:`sketch_radians` function. Coordinates are always rotated around their relative position to the origin. Positive numbers rotate in a clockwise direction and negative numbers rotate in a counterclockwise direction. Transformations apply to everything that happens after and subsequent calls to the function accumulates the effect. For example, calling ``rotate_y(PI/2)`` and then ``rotate_y(PI/2)`` is the same as ``rotate_y(PI)``. If ``rotate_y()`` is run within the ``draw()``, the transformation is reset when the loop begins again. This function requires using ``P3D`` as a third parameter to :doc:`sketch_size` as shown in the example.

Underlying Processing method: `rotateY <https://processing.org/reference/rotateY_.html>`_

Signatures
----------

.. code:: python

    rotate_y(
        angle: float,  # angle of rotation specified in radians
        /,
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

