.. _qgisstylefromproject:

Create style database from project
========================================
Extracts all style objects (symbols, color ramps, text formats and
label settings) from a QGIS project.

The extracted symbols are saved to a QGIS style database (:file:`XML` format),
which can be managed and imported via the :ref:`Style Manager <vector_style_manager>`
dialog.

..
    .. seealso:: :ref:`qgiscombinestyles`

Parameters
----------

Input project : [file]
    Name: ``INPUT``

    Description: A QGIS project file to extract the style items from

Objects to extract : [enumeration] [list]
    Name: ``OBJECTS``

    Description: Types of style items in the input project you would like
    to put in the new database. This can be:

    * 0 --- :ref:`Symbols <edit_symbol>`
    * 1 --- :ref:`Color ramps <color-ramp>`
    * 2 --- :ref:`Text formats <text_format>`
    * 3 --- :ref:`Label settings <showlabels>`

Output style database : [file]
    Name: ``OUTPUT``

    Default: ``[Save to temporary file]``

    Description: Specify the output :file:`.XML` file for the selected items.
    One of:

    .. include:: ../../algs_include.rst
        :start-after: **file_output_types**
        :end-before: **end_file_output_types**

Outputs
-------

Color ramp count : [number]
    Name: ``COLORRAMPS``

    Description: Number of color ramps

Label settings count : [number]
    Name: ``LABELSETTINGS``

    Description: Number of label settings

Output style database : [file]
    Name: ``OUTPUT``

    Description: Output :file:`.XML` file for the selected style items

Symbol count : [number]
    Name: ``SYMBOLS``

    Description: Number of symbols

Text format count : [number]
    Name: ``TEXTFORMATS``

    Description: Number of text formats

Examples
--------
**Todo**

Python code
-----------

**Algorithm ID**: ``native:stylefromproject``

.. code-block:: python

   import processing
   parameters = {} # TODO
   processing.run("native:stylefromproject", parameters)
