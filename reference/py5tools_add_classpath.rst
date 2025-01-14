py5_tools.add_classpath()
=========================

Add a Java jar file to the classpath.

Examples
--------

.. raw:: html

    <div class="example-table">

.. raw:: html

    <div class="example-row"><div class="example-cell-image">

.. raw:: html

    </div><div class="example-cell-code">

.. code:: python

    import py5_tools

    py5_tools.add_jars('path/to/project_jars')
    py5_tools.add_classpath('path/to/jar/file/java_code.jar')

    import py5

    py5.println(py5_tools.get_classpath())

.. raw:: html

    </div></div>

.. raw:: html

    </div>

Description
-----------

Add a Java jar file to the classpath. The path to the file can be absolute or relative.

After the JVM has started, the classpath cannot be changed. This function will throw a ``RuntimeError`` if it is called after the JVM has already started. Use :doc:`py5tools_is_jvm_running` to first determine if the JVM is running.

Signatures
----------

.. code:: python

    add_classpath(
        classpath: Union[Path, str]  # path to Java jar file
    ) -> None

Updated on September 01, 2022 16:36:02pm UTC

