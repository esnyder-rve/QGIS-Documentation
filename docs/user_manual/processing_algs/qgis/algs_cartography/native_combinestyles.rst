.. _qgiscombinestyles:

Combine style databases
=======================================
Combines multiple QGIS style databases into a single style database.
If items of the same type with the same name exist in different source
databases these will be renamed to have unique names in the output combined database.

.. seealso:: :ref:`qgisstylefromproject`

Parameters
----------

Input databases : [file] [list]
    Name: ``INPUT``

    Description: Files containing QGIS style items

Objects to combine : [enumeration] [list]
    Name: ``OBJECTS``

    Description: Types of style items in the input databases you would
    like to put in the new database. These can be:

    * 0 --- :ref:`Symbols <edit_symbol>`
    * 1 --- :ref:`Color ramps <color-ramp>`
    * 2 --- :ref:`Text formats <text_format>`
    * 3 --- :ref:`Label settings <showlabels>`

Output style database : [file]
    Name: ``OUTPUT``

    Default Value: ``[Save to temporary file]``

    - Output :file: `.XML` file combining the selected style items.
      On of:

    .. include:: ../../algs_include.rst
        :start-after: **file_output_types**
        :end-before: **end_file_output_types**

Outputs
-------

Color ramp count : [number]
    Name: ``COLORRAMPS``

    Description: *None*

Label settings count : [number]
    Name: ``LABELSETTINGS``

    Description: *None*

Output style database : [file]
    Name: ``OUTPUT``

    Description: Output :file:`.XML` file combining the selected style items

Symbol count : [number]
    Name: ``SYMBOLS``

    Description: *None*

Text format count : [number]
    Name: ``TEXTFORMATS``

    Description: *None*

Examples
--------

**Todo**

Python code
-----------

**Algorithm ID**: ``native:combinestyles``

