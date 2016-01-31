Calculation
============

|

CalculateObjectsCenter
^^^^^^^^^^^^^^^^^^^^^^^

Calculate objects center.

.. csv-table:: **Parameters**
    :header: Name, Required, Default,Description
    :widths: 10,10,10,70

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    offset,No,"``[0,0,0]``", Offset to calculated result
    toBuffer,Yes,,Buffer to save result

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "CalculateObjectsCenter", 
        "fromBuffer": "selected objects", 
        "toBuffer": "center_location" 
    }

|

CalculateWorldToViewport
^^^^^^^^^^^^^^^^^^^^^^^^^

Given world coordinate, calculate 3D viewpoint coordinate. Note, 3D viewpoint coordinate is different from screen coordinate.


.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes,Object Reference
    pos,No,Position in world coordinate.
    fromBuffer,No,Buffer of world coordinate
    toBuffer,Yes,Save calculate result to buffer

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "CalculateWorldToViewport", 
        "pos": [89,3,45], 
        "toBuffer": "2DCord" 
    }

|


