sin()
=====

Calculates the sine of an angle.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Sketch_sin_0.png
    :alt: example picture for sin()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        a = 0
        for i in range(25):
            py5.line(4*i, 50, 4*i, 50+40*py5.sin(a))
            a += py5.TWO_PI/25

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Calculates the sine of an angle. This function expects the values of the angle parameter to be provided in radians (values from ``0`` to ``TWO_PI``). Values are returned in the range -1 to 1. 

This function makes a call to the numpy ``sin()`` function.

Signatures
----------

.. code:: python

    sin(
        angle: Union[float, npt.ArrayLike]  # angle in radians
    ) -> Union[float, npt.NDArray]

Updated on September 01, 2022 16:36:02pm UTC

