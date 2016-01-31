Scene Level
============

ChangeObjectLevel
^^^^^^^^^^^^^^^^^^^^^^^

Change scene level to given object.

.. note::
    only supports one object as input.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ChangeObjectLevel", 
        "uid":"first floor" 
    }

|

GetCurrentObjectLevel
^^^^^^^^^^^^^^^^^^^^^^^

 Get current level of given object.

.. note::
    only supports one object as input.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer to store command result.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "GetCurrentObjectLevel", 
        "toBuffer":"currentLevel" 
    }

|

GetCurrentObjectLevelClass
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get class name of current level.

.. note::
    only supports one object as input.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer to store command result.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "GetCurrentObjectLevelClass", 
        "toBuffer":"currentLevelClass" 
    }

|

GetCurrentObjectLevelClassId
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get ClassId of current level, note: classId is a number.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer to store command result.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "GetCurrentObjectLevelClassId", 
        "toBuffer":"currentLevelClassId" 
    }

|

SetExpandFloorPlanHeight
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Set floor distance while expanded.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    height,Yes,Floor distance in meters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SetExpandFloorPlanHeight", 
        "height":3 
    }









