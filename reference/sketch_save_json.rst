save_json()
===========

Save JSON data to a file.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    data = dict(mouse_x=[], mouse_y=[])

    def setup():
        py5.size(250, 250)
        py5.stroke_weight(10)


    def draw():
        data['mouse_x'].append(py5.mouse_x)
        data['mouse_y'].append(py5.mouse_y)
        py5.point(py5.mouse_x, py5.mouse_y)
        if py5.frame_count == 600:
            py5.save_json(data, 'data/mouse_positions.json')
            py5.exit_sketch()

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Save JSON data to a file. If ``filename`` is not an absolute path, it will be saved relative to the current working directory (:doc:`sketch_sketch_path`). The saved file can be reloaded with :doc:`sketch_load_json`.

The JSON data is saved using the Python json library with the ``dump`` method, and the ``kwargs`` parameter is passed along to that method.

Signatures
----------

.. code:: python

    save_json(
        json_data: Any,  # json data object
        filename: Union[str, Path],  # filename to save JSON data object to
        **kwargs: dict[str, Any]
    ) -> None

Updated on November 19, 2022 01:41:50am UTC

