begin_raw()
===========

To create vectors from 3D data, use the ``begin_raw()`` and :doc:`sketch_end_raw` commands.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(400, 400, py5.P2D)
        py5.begin_raw(py5.PDF, "raw.pdf")


    def draw():
        py5.line(py5.pmouse_x, py5.pmouse_y, py5.mouse_x, py5.mouse_y)


    def key_pressed():
        if py5.key == ' ':
            py5.end_raw()
            py5.exit_sketch()

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.size(400, 400, py5.P2D)

        with py5.begin_raw(py5.PDF, "/tmp/raw.pdf"):
            py5.rect_mode(py5.CENTER)
            py5.fill("#F00")
            for _ in range(10):
                py5.square(py5.random(py5.width), py5.random(py5.height), 10)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

To create vectors from 3D data, use the ``begin_raw()`` and :doc:`sketch_end_raw` commands. These commands will grab the shape data just before it is rendered to the screen. At this stage, your entire scene is nothing but a long list of individual lines and triangles. This means that a shape created with :doc:`sketch_sphere` function will be made up of hundreds of triangles, rather than a single object. Or that a multi-segment line shape (such as a curve) will be rendered as individual segments.

When using ``begin_raw()`` and :doc:`sketch_end_raw`, it's possible to write to either a 2D or 3D renderer. For instance, ``begin_raw()`` with the ``PDF`` library will write the geometry as flattened triangles and lines, even if recording from the ``P3D`` renderer. 

If you want a background to show up in your files, use ``rect(0, 0, width, height)`` after setting the :doc:`sketch_fill` to the background color. Otherwise the background will not be rendered to the file because the background is not a shape.

This method can be used as a context manager to ensure that :doc:`sketch_end_raw` always gets called, as shown in the last example.

Using ``hint(ENABLE_DEPTH_SORT)`` can improve the appearance of 3D geometry drawn to 2D file formats.

Underlying Processing method: `beginRaw <https://processing.org/reference/beginRaw_.html>`_

Signatures
----------

.. code:: python

    begin_raw(
        raw_graphics: Py5Graphics,  # Py5Graphics object to apply draw commands to
        /,
    ) -> None

    begin_raw(
        renderer: str,  # for example, PDF or DXF
        filename: str,  # filename for output
        /,
    ) -> Py5Graphics

Updated on September 01, 2022 16:36:02pm UTC

