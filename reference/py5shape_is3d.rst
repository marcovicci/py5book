Py5Shape.is3d()
===============

Boolean value reflecting if the shape is or is not a 3D shape.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Py5Shape_is3d_0.png
    :alt: example picture for is3d()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        s = py5.create_shape()
        s.begin_shape()
        s.vertex(30, 20)
        s.vertex(85, 20)
        s.vertex(85, 75)
        s.vertex(30, 75)
        s.end_shape(py5.CLOSE)

        py5.println(s.is2d(), s.is3d())
        py5.shape(s)

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Py5Shape_is3d_1.png
    :alt: example picture for is3d()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(100, 100, py5.P3D)
        s = py5.create_shape()
        s.begin_shape()
        s.vertex(30, 20)
        s.vertex(85, 20)
        s.vertex(85, 75)
        s.vertex(30, 75)
        s.end_shape(py5.CLOSE)

        py5.println(s.is2d(), s.is3d())
        py5.shape(s)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Boolean value reflecting if the shape is or is not a 3D shape.

If the shape is created in a Sketch using the ``P3D`` renderer, this will be ``True``, even if it only uses 2D coordinates.

Underlying Processing method: PShape.is3D

Signatures
----------

.. code:: python

    is3d() -> bool

Updated on September 01, 2022 16:36:02pm UTC

