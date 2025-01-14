noise()
=======

Generate pseudo-random noise values for specific coodinates using Processing's noise algorithm.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_noise_0.png
    :alt: example picture for noise()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import numpy as np


    def setup():
        py5.noise_seed(42)
        py5.noise_detail(4, 0.5)
        x, y = np.meshgrid(np.linspace(0, 5, py5.width), np.linspace(0, 5, py5.height))
        new_pixels = py5.remap(py5.noise(x, y), 0, 1, 0, 255).astype(np.uint8)
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
        py5.noise_seed(42)
        py5.noise_detail(4, 0.5)
        x, y = np.meshgrid(
            np.linspace(
                0, 5, py5.width), np.linspace(
                0, 5, py5.height))


    def draw():
        new_pixels = py5.remap(
            py5.noise(x, y, py5.frame_count / 250), 0, 1, 0, 255).astype(np.uint8)
        py5.set_np_pixels(new_pixels, bands='L')

.. raw:: html

    </div></div>

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        py5.noise_seed(42)
        py5.stroke(0, 10)


    def draw():
        n = py5.remap(py5.noise(py5.frame_count / 100), 0, 1, 0, py5.width)
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
        py5.noise_seed(42)
        xpos = py5.width / 2
        ypos = py5.height / 2


    def draw():
        global xpos, ypos
        py5.background(128)
        xpos = (xpos + py5.noise(py5.frame_count / 250) - 0.5) % py5.width
        ypos = (ypos + py5.noise(500 + py5.frame_count / 250) - 0.5) % py5.height
        py5.square(xpos, ypos, 25)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Generate pseudo-random noise values for specific coodinates using Processing's noise algorithm. Noise functions are random sequence generators that produce a more natural, harmonic succession of numbers compared to the :doc:`sketch_random` method.

In contrast to the :doc:`sketch_random` method, noise is defined in an n-dimensional space, in which each coordinate corresponds to a fixed pseudo-random value (fixed only for the lifespan of the program). The noise value can be animated by moving through the noise space, as demonstrated in the examples. Any dimension can also be interpreted as time. An easy way to animate the noise value is to pass the ``noise()`` method the :doc:`sketch_frame_count` divided by a scaling factor, as is done in a few of the examples.

The generated noise values for this method will typically be between 0 and 1, and can be generated in 1, 2, or 3 dimensions. Py5 also provides the :doc:`sketch_os_noise` method, which generates noise using the OpenSimplex 2 algorithm (smooth version / SuperSimplex). That algorithm generates noise values between -1 and 1, and can be generated in 2, 3, or 4 dimensions. Be aware of both of these differences when modifying your code to switch from one to the other. There are other differences in the character of the noise values generated by both methods, so you'll need to do some experimentation to get the results you want.

The actual noise structure is similar to that of an audio signal, in respect to the method's use of frequencies. Similar to the concept of harmonics in physics, both noise algorithms are computed over several octaves which are added together for the final result.

The nature of the noise values returned can be adjusted with :doc:`sketch_noise_seed` and :doc:`sketch_noise_detail`.

Another way to adjust the character of the resulting sequence is the scale of the input coordinates. As the method works within an infinite space, the value of the coordinates doesn't matter as such; only the distance between successive coordinates is important. As a general rule, the smaller the difference between coordinates, the smoother the resulting noise sequence. Steps of 0.005-0.03 work best for most applications, but this will differ depending on the use case and the noise settings.

Py5's ``noise()`` method can also accept numpy arrays as parameters. It will use broadcasting when needed and calculate the values efficiently. Using numpy array parameters will be much faster and efficient than calling the ``noise()`` method repeatedly in a loop. See the examples to see how this can be done.

Noise generation is a rich and complex topic, and there are many noise algorithms and libraries available that are worth learning about. Early versions of py5 used the Python "noise" library, which can generate noise using the "Improved Perlin Noise" algorithm (as described in Ken Perlin's 2002 SIGGRAPH paper) and the Simplex Noise algorithm (also developed by Ken Perlin). That Python library was removed from py5 because it has some bugs and hasn't had a release in years. Nevertheless, it might be useful to you, and can be installed separately like any other Python package. You can also try the Python library "vnoise", which is a pure Python implementation of the Improved Perlin Noise algorithm. Note that py5 can also employ Java libraries, so consider "FastNoise Lite" to experiment with a large selection of noise algorithms with efficient implementations.

Underlying Processing method: `noise <https://processing.org/reference/noise_.html>`_

Signatures
----------

.. code:: python

    noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

    noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        y: Union[float, npt.NDArray],  # y-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

    noise(
        x: Union[float, npt.NDArray],  # x-coordinate in noise space
        y: Union[float, npt.NDArray],  # y-coordinate in noise space
        z: Union[float, npt.NDArray],  # z-coordinate in noise space
        /,
    ) -> Union[float, npt.NDArray]

Updated on September 01, 2022 16:36:02pm UTC

