shader()
========

Applies the shader specified by the parameters.

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
        global edges
        global img
        py5.size(640, 360, py5.P2D)
        img = py5.load_image("leaves.jpg")
        edges = py5.load_shader("edges.glsl")


    def draw():
        py5.shader(edges)
        py5.image(img, 0, 0)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Applies the shader specified by the parameters. It's compatible with the ``P2D`` and ``P3D`` renderers, but not with the default renderer.

Underlying Processing method: `shader <https://processing.org/reference/shader_.html>`_

Signatures
----------

.. code:: python

    shader(
        shader: Py5Shader,  # name of shader file
        /,
    ) -> None

    shader(
        shader: Py5Shader,  # name of shader file
        kind: int,  # type of shader, either POINTS, LINES, or TRIANGLES
        /,
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

