ratio_top
=========

Height of the top section of the window that does not fit the desired aspect ratio of a scale invariant Sketch.

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
      py5.window_resizable(True)
      py5.window_ratio(1280, 720)

      py5.cursor(py5.CROSS)
      py5.stroke_weight(10)


    def draw():
      py5.background(255, 0, 0)
      py5.fill(255)
      py5.rect(0, 0, py5.rwidth, py5.rheight)

      py5.fill(0)
      py5.text_align(py5.CENTER, py5.CENTER)
      x, y = py5.rwidth / 2, py5.rheight / 2
      py5.text_size(200)
      py5.text(f'{py5.rmouse_x}, {py5.rmouse_y}', x, y - 100)
      py5.text_size(100)
      py5.text(f'top={int(py5.ratio_top)} left={int(py5.ratio_left)}', x, y + 100)
      py5.text(f'scale={round(py5.ratio_scale, 3)}', x, y + 200)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Height of the top section of the window that does not fit the desired aspect ratio of a scale invariant Sketch. This will always be greater than or equal to zero. Experimenting with the example and seeing how this value changes will provide more understanding than what can be explained with words. See :doc:`sketch_window_ratio` for more information about how to activate scale invariant drawing and why it is useful.

Underlying Processing field: ratioTop

Updated on September 01, 2022 16:36:02pm UTC

