.. _qgisatlaslayouttomultiplepdf:

Export atlas layout as PDF (multiple files)
===========================================

Exports the atlas of a print layout to multiple PDF files.

If a coverage layer is set, the selected layout's atlas settings exposed
in this algorithm will be overwritten. In this case, an empty filter or
sort by expression will turn those settings off.

Parameters
----------

Basic parameters
................

Atlas layout : [layout]
    Name: ``LAYOUT``

    Description: Layout to export

Coverage layer : [vector: any] : *Optional*
    Name: ``COVERAGE_LAYER``

    Description: Layer to use to generate the atlas
    
Filter expression : [expression]
    Name: ``FILTER_EXPRESSION``

    Description: Expression to use to filter out atlas features

Sort expression : [expression] : *Optional*
    Name: ``SORTBY_EXPRESSION``

    Description: Expression to use to sort the atlas features

Reverse sort order : [boolean] : *Optional*
    Name: ``SORTBY_REVERSE``

    Description: Determins if sorting should be inverted. Used when a sort expression is provided.

Outout filename : [expression] : *Optional*
    Name: ``OUTPUT_FILENAME``

    Description: Name pattern of the PDF outout files.

Output folder : [folder]
    Name: ``OUTPUT_FOLDER``

    Description: Destination folder for the output PDF files.

Advanced parameters
*******************

Map layers to assign to unlocked map item(s) : [enumeration] [layer] : *Optional*
    Name: ``LAYERS``

    Description: Layers to display in the map item(s) whose contents are not locked.

DPI : [number] : *Optional*
    Name: ``DPI``

    Description: DPI of the output file(s). If not set, the value in the print layout settings will be used.
   
	* - **Always export as vectors**
     - ``FORCE_VECTOR``
     - [boolean]

       Default: False
     - Determines if vectorial data should be left as vectors
   
	* - **Always export as raster**
     - ``FORCE_RASTER``
     - [boolean]

       Default: False
     - Forces all the items in the map to be rasterized.
       This parameter takes precedence over the ``FORCE_VECTOR`` parameter.
   
	* - **Append georeference information**
     - ``GEOREFERENCE``
     - [boolean]

       Default: True
     - Determines if a world file should be generated
   
	* - **Export RDF metadata**
     - ``INCLUDE_METADATA``
     - [boolean]

       Default: True
     - Determines if RDF metadata (title, author, ...) should be generated
   
	* - **Disable tiled raster layer exports**
     - ``DISABLE_TILED``
     - [boolean]

       Default: False
     - Determines if raster should be tiled
   
	* - **Simplify geometries to reduce output file size**
     - ``SIMPLIFY``
     - [boolean]

       Default: True
     - Determines if geometries should be simplified to reduce output file size
   
	* - **Text export**
     - ``TEXT_FORMAT``
     - [enumeration]

       Default: 0
     - Determines if text should be exported as path or text objects.
       Possible options are:

       
	* 0 - Always export text as paths (recommended)
       
	* 1 - Always export texts as text objects
   
	* - **Image compression**
     - ``IMAGE_COMPRESSION``
     - [enumeration]

       Default: 0
     - Determines compression level of the image and how suitable the file could be
       for printing outputs or post-production in external applications.
       Possible options are:

       * 0 - Lossy (JPEG)
       * 1 - Lossless

Outputs
.......

.. list-table::
   :header-rows: 1
   :widths: 20 20 20 40

   * - Label
     - Name
     - Type
     - Description
   * - **PDF file**
     - ``OUTPUT``
     - [file]
     - PDF file corresponding to the exported atlas layout

Python code
...........

**Algorithm ID**: ``native:atlaslayouttomultiplepdf``

.. include:: ../algs_include.rst
  :start-after: **algorithm_code_section**
  :end-before: **end_algorithm_code_section**

