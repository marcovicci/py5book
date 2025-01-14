Py5Image.height
===============

The height of the image in units of pixels.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Py5Image_height_0.png
    :alt: example picture for height

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        tiles = py5.load_image("tiles.jpg")
        py5.image(tiles, 20, 10)
        py5.rect(55, 10, tiles.width, tiles.height)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

The height of the image in units of pixels.

Underlying Processing field: `PImage.height <https://processing.org/reference/PImage_height.html>`_

Updated on September 01, 2022 16:36:02pm UTC

