update_pixels()
===============

Updates the display window with the data in the :doc:`sketch_pixels` array.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_update_pixels_0.png
    :alt: example picture for update_pixels()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        img = py5.load_image("rockies.jpg")
        py5.image(img, 0, 0)
        half_image = img.width * img.height//2
        py5.load_pixels()
        for i in range(0, half_image):
            py5.pixels[i+half_image] = py5.pixels[i]
    
        py5.update_pixels()

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Updates the display window with the data in the :doc:`sketch_pixels` array. Use in conjunction with :doc:`sketch_load_pixels`. If you're only reading pixels from the array, there's no need to call ``update_pixels()`` — updating is only necessary to apply changes.

Underlying Processing method: `updatePixels <https://processing.org/reference/updatePixels_.html>`_

Signatures
----------

.. code:: python

    update_pixels() -> None

    update_pixels(
        x1: int,  # x-coordinate of the upper-left corner
        y1: int,  # y-coordinate of the upper-left corner
        x2: int,  # width of the region
        y2: int,  # height of the region
        /,
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

