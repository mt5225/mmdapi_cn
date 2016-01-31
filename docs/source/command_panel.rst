Command Panel
=============

|

ClearCmdPanel
^^^^^^^^^^^^^^^^^^^^^^^

Clear command panel.

**Parameters**

No Parameters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ClearCmdPanel"
    }

|

AddToCmdPanel
^^^^^^^^^^^^^^

Add command to command panel.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    cmds,Yes,Command or command array to be added to panel
    execute,No,If run command after add

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "AddToCmdPanel", 
        "cmds":[ 
            {"cmd":"clearSelection" } 
        ],
        "execute":false 
    }

|

RemoveFromCmdPanel
^^^^^^^^^^^^^^^^^^^

Remove command from command panel.

.. note::
    Command name must be identical.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    cmds,Yes,Command or command array to be removed from panel

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "RemoveFromCmdPanel", 
        "cmds":[ 
            {"cmd":"clearSelection" } 
        ]
    }



