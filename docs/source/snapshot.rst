Snapshot
=========

|

Snapshot
^^^^^^^^^^^

Get and save snapshot.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    name,Yes,Name of snapshot
    isSaveToServer,No,If save snapshot to server
    isShowIn3D,No, If show snapshot in menu
    jsonToBuffer,No,Save snapshot to buffer in json format


**Example**

* Set a snapshot

.. code-block:: json
    :linenos:

    {
        "cmd": "Snapshot", 
        "name":"my workspace", 
        "isSaveToServer": true, 
        "isShowIn3D": false 
    }

* Get snapshot data and save to buffer

.. code-block:: json
    :linenos:

    {
        "cmd": "Snapshot", 
        "name":"name", 
        "jsonToBuffer": "SnapshotBuffer"
    }

|

SnapshotRecoverByName
^^^^^^^^^^^^^^^^^^^^^^^

Recover snapshot by name.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    name,Yes, Snapshot name


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SnapshotRecoverByName", 
        "name":"my workspace" 
    }

|

SnapshotRecoverByJson
^^^^^^^^^^^^^^^^^^^^^^^

Recover snapshot by name.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    json,Yes,json data


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SnapshotRecoverByJson", 
        "name":"my workspace" 
    }

|

PlaySnapshotAnimByName
^^^^^^^^^^^^^^^^^^^^^^^

Recover snapshot by name.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    name,Yes,Name of animation


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "PlaySnapshotAnimByName", 
        "name":"check01" 
    }

|

PlaySnapshotAnimByName
^^^^^^^^^^^^^^^^^^^^^^^

Stop snapshot animation.

**Parameters**

No Parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "StopSnapshotAnim" 
    }


























