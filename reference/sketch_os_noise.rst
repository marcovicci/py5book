os_noise()
==========

Generate pseudo-random noise values for specific coodinates using the OpenSimplex 2 algorithm (smooth version / SuperSimplex).

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_os_noise_0.png
    :alt: example picture for os_noise()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import numpy as np


    def setup():
        py5.os_noise_seed(42)
        x, y = np.meshgrid(np.linspace(0, 5, py5.width), np.linspace(0, 5, py5.height))
        new_pixels = py5.remap(py5.os_noise(x, y), -1, 1, 0, 255).astype(np.uint8)
        py5.set_np_pixels(new_pixels, bands='L')

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import numpy as np


    def setup():
        global x, y
        py5.size(200, 200)
        py5.os_noise_seed(42)
        x, y = np.meshgrid(
            np.linspace(
                0, 5, py5.width), np.linspace(
                0, 5, py5.height))


    def draw():
        new_pixels = py5.remap(
            py5.os_noise(py5.frame_count / 100, x, py5.frame_count / 100, y), -1, 1, 0, 255).astype(np.uint8)
        py5.set_np_pixels(new_pixels, bands='L')

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.os_noise_seed(42)
        py5.stroke(0, 10)


    def draw():
        n = py5.remap(py5.os_noise(0.2, py5.frame_count / 100), -1, 1, 0, py5.width)
        py5.line(n, 0, n, py5.height)

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        global xpos, ypos
        py5.rect_mode(py5.CENTER)
        py5.os_noise_seed(42)
        xpos = py5.width / 2
        ypos = py5.height / 2


    def draw():
        global xpos, ypos
        py5.background(128)
        xpos = (xpos + py5.os_noise(0.2, py5.frame_count / 250)) % py5.width
        ypos = (ypos + py5.os_noise(5.8, py5.frame_count / 250)) % py5.height
        py5.square(xpos, ypos, 25)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Generate pseudo-random noise values for specific coodinates using the OpenSimplex 2 algorithm (smooth version / SuperSimplex). Noise functions are random sequence generators that produce a more natural, harmonic succession of numbers compared to the :doc:`sketch_random` method.

In contrast to the :doc:`sketch_random` method, noise is defined in an n-dimensional space, in which each coordinate corresponds to a fixed pseudo-random value (fixed only for the lifespan of the program). The noise value can be animated by moving through the noise space, as demonstrated in the examples. Any dimension can also be interpreted as time. An easy way to animate the noise value is to pass the ``os_noise()`` method the :doc:`sketch_frame_count` divided by a scaling factor, as is done in a few of the examples.

The generated noise values for this method will be between -1 and 1, and can be generated in 2, 3, or 4 dimensions. To generate noise in 1 dimension, add a constant value as an extra parameter, as shown in a few examples. Py5 also provides the :doc:`sketch_noise` method, which generates noise using Processing's noise algorithm. That algorithm typically generates noise values between 0 and 1, and can be generated in 1, 2, or 3 dimensions. Be aware of both of these differences when modifying your code to switch from one to the other. There are other differences in the character of the noise values generated by both methods, so you'll need to do some experimentation to get the results you want.

The nature of the noise values returned can be adjusted with :doc:`sketch_os_noise_seed`.

Another way to adjust the character of the resulting sequence is the scale of the input coordinates. As the method works within an infinite space, the value of the coordinates doesn't matter as such; only the distance between successive coordinates is important. As a general rule, the smaller the difference between coordinates, the smoother the resulting noise sequence. Steps of 0.005-0.03 work best for most applications, but this will differ depending on the use case and the noise settings.

Py5's ``os_noise()`` method can also accept numpy arrays as parameters. It will use broadcasting when needed and calculate the values efficiently. Using numpy array parameters will be much faster and efficient than calling the ``os_noise()`` method repeatedly in a loop. See the examples to see how this can be done. The noise algorithm for this method is implemented in Java.

Noise generation is a rich and complex topic, and there are many noise algorithms and libraries available that are worth learning about. Early versions of py5 used the Python "noise" library, which can generate noise using the "Improved Perlin Noise" algorithm (as described in Ken Perlin's 2002 SIGGRAPH paper) and the Simplex Noise algorithm (also developed by Ken Perlin). That Python library was removed from py5 because it has some bugs and hasn't had a release in years. Nevertheless, it might be useful to you, and can be installed separately like any other Python package. You can also try the Python library "vnoise", which is a pure Python implementation of the Improved Perlin Noise algorithm. Note that py5 can also employ Java libraries, so consider "FastNoise Lite" to experiment with a large selection of noise algorithms with efficient implementations.

Signatures
----------

.. code:: python

    os_noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        y: Union[float, npt.NDArray],  # y-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

    os_noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        y: Union[float, npt.NDArray],  # y-coordinate in noise space
        z: Union[float, npt.NDArray],  # z-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

    os_noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        y: Union[float, npt.NDArray],  # y-coordinate in noise space
        z: Union[float, npt.NDArray],  # z-coordinate in noise space
        w: Union[float, npt.NDArray],  # w-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

Updated on September 01, 2022 16:36:02pm UTC

