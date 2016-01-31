Logic
======

RegTimer
^^^^^^^^^^^

Timer register.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    name,Yes,Name of timer
    time,No, Timeout in seconds
    loop,No, If loop
    cmds,No,Command to be executed at timeout


**Example**

* Set a snapshot

.. code-block:: json
    :linenos:

    {
        "cmd": "RegTimer", 
        "name":"ExplodeWhenTimeout", 
        "loop":false, 
        "cmds":[
            { "cmd": "CreatePlacement", "uid" : "Explode", "bundleId":"C2F0A5FB249A4F4C9D7A46E4876E2F4C", "pos":[0,0,0]} 
        ]
    }

|

UnregTimer
^^^^^^^^^^^^^^^^^^^^^^^

Unregister timer.

**Parameters**

No Parameters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "UnregTimer", 
        "name":"ExplodeWhenTimeout" 
    }

|

CheckBoolean
^^^^^^^^^^^^^

Pass boolean value from buffer, then run command depends on boolean value.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    fromBuffer,Yes, Buffer to get boolean value
    trueCmds,No, Command to run if ``true``
    falseCmds,No, Command to run if ``false``


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "CheckBoolean", 
        "fromBuffer":"resultBuffer",
        "trueCmds":[
            {"cmd":"SetColor",   "uid":"obj01",   "color":[1,0,0] }
        ], 
        "falseCmds":[
            {"cmd":"SetColor",   "uid":"obj01",   "color":[0,1,0] }
        ] 
    }





