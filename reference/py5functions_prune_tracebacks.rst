prune_tracebacks()
==================

Set py5's exception handling to prune unhelpful stack trace frames when exceptions are thrown by a running Sketch.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import py5
    py5.prune_tracebacks(False)

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Set py5's exception handling to prune unhelpful stack trace frames when exceptions are thrown by a running Sketch. When using any Python library, exceptions are often thrown from within the library itself, resulting in stack traces that are a combination of the user's code and the library's own code. Often times the stack traces contributed by the library's code are not helpful to users because the users are not familiar with that code and/or those stack frames do not provide useful debugging information. This is particularly the case for py5, where most of the real functionality is provided by Processing's Java libraries and many of py5's methods are essentially thin wrappers making calls to Java. By default, py5 will prune its own stack trace frames from error messages. Almost always this is helpful, but when investigating bugs in py5 itself, sometimes it is helpful to turn off this feature.

Signatures
----------

.. code:: python

    prune_tracebacks(
        prune: bool,  # prune exception tracebacks
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

