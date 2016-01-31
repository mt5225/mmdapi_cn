Resource
=========

|

DownloadBundle
^^^^^^^^^^^^^^^

Download model.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    bundleId,Yes, Model Id
    cmds,No,Callback command after download

**Example**

* Change object model after download

.. code-block:: json
    :linenos:

    {
        "cmd": "DownloadBundle", 
        "bundleId":"F933B1A524B94050BC7A82B15D2057F5", 
        "cmds":[{ 
            "cmd":"ChangePlacementBundle", 
            "uid":"object01",
            "bundleId":"F933B1A524B94050BC7A82B15D2057F5" 
        }]
    }

|

ChangePlacementBundle
^^^^^^^^^^^^^^^^^^^^^^

Change object model.

.. _note:
    Model must be downloaded or used in scene.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    bundleId,Yes,Model ID

**Example**

* Change object model

.. code-block:: json
    :linenos:

    {
        "cmd":"ChangePlacementBundle", 
        "uid":"object01",
        "bundleId":"F933B1A524B94050BC7A82B15D2057F5" 
    }

|

DownloadTexture
^^^^^^^^^^^^^^^^^^^^^^

Download texture.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    url,Yes,"URL to download texture, can be relative path based on mmd server URL"
    cmds,Yes,Callback command after download

**Example**

* Change object texture after download

.. code-block:: javascript
    :linenos:

    {
        "cmd": "DownloadTexture", 
        "url":"images/selection.png", //URL or relative path based on mmd server URL
        "cmds":[{ 
            "cmd":"ChangePlacementTexture", 
            "uid":"object01",
            "url":"images/selection.png" 
        }]
    }

|

ChangePlacementTexture
^^^^^^^^^^^^^^^^^^^^^^^

Change texture of object.

.. _note:
    texture must be downloaded or used in scene.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    url,Yes,"Texture URL, or relative path based on mmd server URL"

**Example**

* Change texture of object

.. code-block:: json
    :linenos:

    {
        "cmd":"ChangePlacementTexture", 
        "uid":"object01",
        "url":"images/selection.png" 
    }




