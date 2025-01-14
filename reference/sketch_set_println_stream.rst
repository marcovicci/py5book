set_println_stream()
====================

Customize where the output of :doc:`sketch_println` goes.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import ipywidgets as widgets
    from IPython.display import display


    class WidgetPrintlnStream:

        def init(self):
            self.out = widgets.Output(layout=dict(
                max_height='200px', overflow='auto'))
            display(self.out)

        def print(self, text, end='\n', stderr=False):
            if stderr:
                self.out.append_stderr(text + end)
            else:
                self.out.append_stdout(text + end)


    py5.set_println_stream(WidgetPrintlnStream())

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Customize where the output of :doc:`sketch_println` goes.

When running a Sketch asynchronously through Jupyter Notebook, any ``print`` statements using Python's builtin function will always appear in the output of the currently active cell. This will rarely be desirable, as the active cell will keep changing as the user executes code elsewhere in the notebook. The :doc:`sketch_println` method was created to provide users with print functionality in a Sketch without having to cope with output moving from one cell to the next. Use ``set_println_stream`` to change how the output is handled. The ``println_stream`` object must provide ``init()`` and ``print()`` methods, as shown in the example. The example demonstrates how to configure py5 to output text to an IPython Widget.

Signatures
----------

.. code:: python

    set_println_stream(
        println_stream: Any,  # println stream object to be used by println method
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

