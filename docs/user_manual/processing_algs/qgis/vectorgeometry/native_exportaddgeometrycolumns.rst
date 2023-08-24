.. _qgisexportaddgeometrycolumns:

Add geometry attributes
=======================
Computes geometric properties of the features in a vector layer and
includes them in the output layer.

It generates a new vector layer with the same content as the input one,
but with additional attributes, containing geometric measurements
based on a selected CRS.

The attributes added to the table depend on the geometry type and
dimension of the input layer:

* for **point** layers: X (``xcoord``), Y (``ycoord``), Z (``zcoord``)
  coordinates and/or M value (``mvalue``)
* for **line** layers: ``length`` and, for the LineString and
  CompoundCurve geometry types, the feature ``sinuosity`` and straight
  distance (``straightdis``)
* for **polygon** layers: ``perimeter`` and ``area``

**Default menu**: :menuselection:`Vector --> Geometry Tools`

Parameters
----------

Input layer : [vector:any]
    Name: ``INPUT``

    Description: Input vector layer

Calculate using : [enumeration]
    Name: ``CALC_METHOD``

    Default Value: 0 (Layer CRS)

    Description: Calculation parameters to use for the geometric properties. Options are:

    * 0 --- Layer CRS
    * 1 --- Project CRS
    * 2 --- Ellipsoidal

Added geom info : [same as input]
    Name: ``OUTPUT``

    Default Value: ``[Create temporary layer]``

    Description: Specify the output (input copy with geometry) layer. One of:
    
    .. include:: ../../algs_include.rst
       :start-after: **layer_output_types**
       :end-before: **end_layer_output_types**

Outputs
-------

Added geom info : [same as input]
    Name: ``OUTPUT``

    Description: Copy of the input vector layer with the addition of the geometry fields

Examples
--------

**Todo**

Python code
-----------

**Algorithm ID**: ``qgis:exportaddgeometrycolumns``

.. code-block:: python

   import processing
   parameters = {} # Todo
   processing.run("qgis:exportaddgeometrycolumns", parameters)
