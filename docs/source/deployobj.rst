Deploy Object
==============

|

Deploy
^^^^^^^

Specify model set available in current environment.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 10,10,10,70

    enable,No,``true``,"If ``true``, enable, if ``false``, disable"
    item,No,,Array of model IDs

**Example**

* Deploy Model

.. code-block:: json
    :linenos:

    {
        "cmd": "Deploy", 
        "items":[ 
            "614AC0466F4E48B792CC83A5B99AF4FC", 
            "F933B1A524B94050BC7A82B15D2057F5", 
        ]
    }

* Disable

.. code-block:: json
    :linenos:

    {
        "cmd": "Deploy", 
        "enable":false 
    }

|

SetDragPlacementParamInDeploy
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Effect setting during drag and drop.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    absorbPlacement,No,"If object being drag can be attached by target object automatically."
    absorbNormal,No,"If object being drag align to normal line of target object automatically."
    absorbPivot,No,"If object being drag align to axis line of target object automatically."

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd":"SetDragPlacementParamInDeploy", 
        "absorbPlacement":true,
        "absorbNormal":false, 
        "absorbPivot":true 
    }

|

GetDeployObjects
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get deploy objects and save to buffer.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer to store objects

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd":"GetDeployObjects", 
        "toBuffer":{"ObjectManager":"RunBuffer/deployObjects"}
    }

|

GetDeployToJson
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get deploy objects and save to buffer in JSON format.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer to store objects

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd":"GetDeployToJson", 
        "toBuffer":{"ObjectManager":"RunBuffer/deployObjects"}
    }

|

SetDeployFromJson
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Deploy objects from JSON

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    json,Yes,JSON data

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd":"SetDeployFromJson", 
        "json":{
                "2345223":{
                    "bundle":"3268DD250B694147B0BDB37FA390BF96",
                    "floor":"floor01",
                    "pos":"0.22 0.33 1.34", //position
                    "rot":"0 0 0",//rotation
                    "scl":"1 1 1",//scale
                    "properties":{
                        "UserID":"Camera01",
                        "PropertyDict":{
                            "Operator":"wxz"
                        }
                    }
                }
            }
    }

|

ClearDeployObjects
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Get deploy objects and save to buffer in JSON format.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 10,10,10,70

    destroyObjects,Yes,``true``, "Clear objects in scene, if ``true``, will clear objects both in Deploy module and scene, if ``false``, only clear objects in Deploy module, and keep objects in scene."

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd":"ClearDeployObjects"
    }










