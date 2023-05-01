Align points to features
========================

Calculates the rotation required to align point features with their nearest
feature from another reference layer. A new field is added to the output layer
which is filled with the angle (in degrees, clockwise) to the nearest reference
feature.

Optionally, the output layer's symbology can be set to automatically use the
calculated rotation field to rotate marker symbols.
If desired, a maximum distance to use when aligning points can be set,
to avoid aligning isolated points to distant features.

.. figure:: img/angletonearest_detail.png
    :align: center
    :figwidth: image

    The above image shows an SVG symbol at it's default rotation (facing up).
    The rotation value produced by this algorithm will make the symbol's top face the referenced layer feature.
    The symbol rotation data-defined override expression produced by this tool may need to be changed if this is
    not the desired behavior.

.. hint:: This algorithm is designed for use cases like aligning building
   point symbols to follow the nearest road direction. See example 1 for details.

|checkbox| Allows :ref:`features in-place modification <processing_inplace_edit>`
of point features

Parameters
----------

Input Layer : [vector: point]
    Name: ``INPUT``

    Description: Point features to calculate the rotation for

Reference layer : [vector: any]
    Name: ``REFERENCE_LAYER``

    Description: Layer to find the closest feature for rotation calculation

Maximum distance to consider : [number] : *Optional*
    Name: ``MAX_DISTANCE``

    Description: If no reference feature is found within this distance, no rotation is assigned to the point feature

Angle field name : [string]
    Name: ``FIELD_NAME``

    Default Value: 'rotation'

    Description: Field in which to store the rotation value

Automatically apply symbology : [boolean]
    Name: ``APPLY_SYMBOLOGY``

    Default Value: True

    Description: Rotates the symbol marker of the features using the angle field value

Aligned layer : [vector: point]
    Name: ``OUTPUT``

    Default Value: ``[Save to temporary file]``

    Description: Specify the rotated output vector layer. One of:

    .. include:: ../../algs_include.rst
        :start-after: **layer_output_types**
        :end-before: **end_layer_output_types**

Outputs
-------

Aligned layer : [vector: point]
    Name: ``OUTPUT``

    Default Value: ``[Save to temporary file]``

    Description: The point layer appended with a rotation field. If loaded to QGIS, it is applied by default the input layer symbology, with a data-defined rotation of its marker symbol.

Examples
--------

**Example 1: Aligning house symbols to roads**

.. figure:: img/angletonearest_example01_before.png
    :scale: 50 %

    A point layer symbolized with a house svg symbol that we want to rotate
    to face the roads (line layer).

.. figure:: img/angletonearest_example01_after.png
    :scale: 50%

    The rotated symbols will at first have the house peaks facing the roads,
    but modifying the symbol expression by adding 180 to the symbol rotation
    field value will flip the houses to now face the roads.

Python code
-----------

**Algorithm ID**: ``native:angletonearest``

.. code-block:: python
    
    import processing
    parameters = {
    'INPUT': mySourceLayer,
    'REFERENCE_LAYER': myRefLayer,
    'FIELD_NAME': 'symbol_rotation',
    'APPLY_SYMBOLOGY': True}
    processing.run("native:angletonearest", parameters)

.. Substitutions definitions - AVOID EDITING PAST THIS LINE
   This will be automatically updated by the find_set_subst.py script.
   If you need to create a new substitution manually,
   please add it also to the substitutions.txt file in the
   source folder.

.. |checkbox| image:: /static/common/checkbox.png
   :width: 1.3em
