.. _qgiscategorizeusingstyle:

Create categorized renderer from styles
=======================================
Sets a vector layer's renderer to a categorized renderer using matching symbols
from a style database. If no style file is specified, symbols from the user's
current :ref:`symbol library <vector_symbol_library>` are used instead.

A specified expression or field is used to create categories for the renderer.
Each category is individually matched to the symbols which exist within
the specified QGIS XML style database. Whenever a matching symbol name is found,
the category's symbol will be set to this matched symbol.

If desired, outputs can also be tables containing lists of the categories which
could not be matched to symbols, and symbols which were not matched to categories.

Parameters
----------

Input layer : [vector: any]
    Name: ``INPUT``

    Description: Vector layer to apply a categorized style to


Categorize using expression : [expression]
    Name: ``FIELD``

    Description: Field or expression to categorize the features

Style datbase : [file]
    Name: ``STYLE``

    Description: File (:file:`.XML`) containing the symbols to
    apply to the input layer categories. Leave blank to use
    saved symbols. The file can also be obtained from the Style
    Manager :ref:`Share symbols <share_symbols>` tool. If no file
    is specified, QGIS local symbols library is used.

Use case-sensitive match to symbol names : [boolean]
    Name: ``CASE_SENSITIVE``

    Default Value: False

    Description: If True (checked), applies a case sensitive
    comparison between the categories and symbols names

Ignore non-alphanumeric characters while matching : [boolean]
    Name: ``TOLERANT``

    Default Value: False

    Description: If True (checked), non-alphanumeric characters in
    the categories and symbols names will be ignored, allowing
    greater tolerance during the match.

Non-matching categories : [table] : *Optional*
    Name: ``NON_MATCHING_CATEGORIES``

    Default Value: ``[Skip output]``

    Description: Output table for categories which do not match any
    symbol in the database. One of:

    .. include:: ../../algs_include.rst
        :start-after: **layer_output_types_skip**
        :end-before: **end_layer_output_types_skip**

Non-matching symbol names : [table] : *Optional*
    Name: ``NON_MATCHING_SYMBOLS``

    Default Value: ``[Skip output]``

    Description: Output table for symbols from the proided style
    database which do not match any category. One of:

    .. include:: ../../algs_include.rst
        :start-after: **layer_output_types_skip**
        :end-before: **end_layer_output_types_skip**

Outputs
-------

Non-matching categories : [table] : *Optional*
    Name: ``NON_MATCHING_CATEGORIES``

    Default Value: ``[Skip output]``

    Description: Output table for categories which do not match any
    symbol in the database. One of:

    .. include:: ../../algs_include.rst
        :start-after: **layer_output_types_skip**
        :end-before: **end_layer_output_types_skip**

Non-matching symbol names : [table] : *Optional*
    Name: ``NON_MATCHING_SYMBOLS``

    Default Value: ``[Skip output]``

    Description: Output table for symbols from the proided style
    database which do not match any category. One of:

    .. include:: ../../algs_include.rst
        :start-after: **layer_output_types_skip**
        :end-before: **end_layer_output_types_skip**

Categorized layer : [same as input]
    Name: ``OUTPUT``

    Description: The input vector layer with the categorized style
    applied. No new layer is output.

Examples
--------

**Todo**

Python code
-----------

**Algorithm ID**: ``native:categorizeusingstyle``

.. code-block:: python

   import processing
   parameters = {} # TODO
   processing.run("native:categorizeusingstyle", parameters)
