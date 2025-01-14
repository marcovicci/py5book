lines()
=======

Draw a collection of lines to the screen.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_lines_0.png
    :alt: example picture for lines()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import numpy as np

    def setup():
        random_lines = 100 * np.random.rand(50, 4)
        py5.lines(random_lines)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Draw a collection of lines to the screen. The purpose of this method is to provide an alternative to repeatedly calling :doc:`sketch_line` in a loop. For a large number of lines, the performance of ``lines()`` will be much faster.

The ``coordinates`` parameter should be a numpy array with one row for each line. The first few columns are for the first point of each line and the next few columns are for the second point of each line. There will be four or six columns for 2D or 3D points, respectively.

Underlying Processing method: lines

Signatures
----------

.. code:: python

    lines(
        coordinates: npt.NDArray[np.floating],  # 2D array of line coordinates with 4 or 6 columns for 2D or 3D points, respectively
        /,
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

