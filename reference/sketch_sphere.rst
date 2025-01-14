sphere()
========

A sphere is a hollow ball made from tessellated triangles.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_sphere_0.png
    :alt: example picture for sphere()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(100, 100, py5.P3D)
        py5.no_stroke()
        py5.lights()
        py5.translate(58, 48, 0)
        py5.sphere(28)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

A sphere is a hollow ball made from tessellated triangles.

Underlying Processing method: `sphere <https://processing.org/reference/sphere_.html>`_

Signatures
----------

.. code:: python

    sphere(
        r: float,  # the radius of the sphere
        /,
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

