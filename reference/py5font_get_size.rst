Py5Font.get_size()
==================

Get the font's size.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. image:: /images/reference/Py5Font_get_size_0.png
    :alt: example picture for get_size()

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    def setup():
        font = py5.create_font('DejaVu Sans', 15)
        py5.text_font(font)

        py5.text(font.get_name(), 5, 20)
        py5.text(font.get_post_script_name(), 5, 40)
        py5.text(font.get_size(), 5, 60)
        py5.text(font.get_default_size(), 5, 80)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Get the font's size.

Underlying Processing method: PFont.getSize

Signatures
----------

.. code:: python

    get_size() -> int

Updated on September 01, 2022 16:36:02pm UTC

