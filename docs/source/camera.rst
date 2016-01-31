Camera
=======

|

SwitchCameraTo3D
^^^^^^^^^^^^^^^^^^^

Viewpoint switch between 3D and 2D.

.. note::
    Same as 3D/2D switch button in control panel

.. csv-table:: **Parameters**
    :header: Name, Required, Default,Description
    :widths: 10,10,10,70

    enable,No,``true``,"If ``true``, switch to 3D, if ``false``, switch to 2D"
    
|

CameraFitToSelection
^^^^^^^^^^^^^^^^^^^^^^

Fit to selected object, if no object is selected, fit to current layer.


**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "CameraFitToSelection" 
    }

|

SetOrbitCameraParam
^^^^^^^^^^^^^^^^^^^^^^

Camera parameters setting.

.. csv-table:: **Parameters**
    :header: Name, Required, Default,Description
    :widths: 10,10,30,60

    heightLimit,No,"``[0,1500]``","Height limit setting, take two array as input, first array as minimum height, second array as maxium height."
    zoomLimit,No,"``[0.1,1000]``","Limits on back and froths moving through mouse wheel. take one array as input, first element in array sets closest distance to viewpoint, second viewpoint sets farthest distance from viewpoint."
    farClipDistance,No,change with height attribute,"Far clip distance setting, for animation effects only"
    nearClipDistance,No,change with height attribute,"Near clip distance setting, for animation effects only"
    smooth,No,``true``,"Flying camera in smooth mode, if set to false, camera will fly straight."

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SetOrbitCameraParam", 
        "heightLimit":[0, 5500], 
        "zoomLimit":[0, 15500], 
        "farClipDistance":5000, 
        "nearClipDistance":0.2, 
        "smooth":true  
    }

|

CameraFlyToBest
^^^^^^^^^^^^^^^

Fly to optimized viewpoint of given object.

.. note::
    Only accept one object as input

.. csv-table:: **Parameters**
    :header: Name, Required, Default,Description
    :widths: 10,10,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    time,No,2,"Fly time, in seconds"
    offset,No,"``[0,0,0]``","Optimized viewpoint plus offset as camera location.

    .. note::
        Offset is calculated in world coordinate.
    "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "CameraFlyToBest", 
        "uid":"object01",
        "time":3, 
        "offset":[0.0, 1.0, 0.0] //move up another 1 meter.
    }

|

CameraFitToBest
^^^^^^^^^^^^^^^

Move camera to optimized viewpoint of given object, no flying process.

.. note::
    Only accept one object as input

.. csv-table:: **Parameters**
    :header: Name, Required, Default,Description
    :widths: 10,10,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    time,No,2,"Fly time, in seconds"
    offset,No,"``[0,0,0]``","Optimized viewpoint plus offset as camera location.

    .. note::
        Offset is calculated in world coordinate.
    "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "CameraFitToBest", 
        "uid":"object01",
        "time":3, 
        "offset":[0.0, 1.0, 0.0] //move up another 1 meter.
    }



