Event
=====

|

.. _regevent-label:

RegEvent
^^^^^^^^^

Event Register.

.. note:: 
    Use id or uid for object reference

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 10,10,10,70

    id,No,,Object id
    uid,No,,Object uid(UserID)
    condition,No,,Trigger condition
    event,Yes,,"Trigger event, to avoid conflict, use / to separate callbacks, for instance, AddToSelection/callBack1 
    see :ref:`Event List <event-list-label>`"
    priority,No,50,"Event with higher priority will be trigger first"
    cmds,Yes,,Callback commands


**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "RegEvent", 
        
        //"_default_" means always trigger 
        //"condition": "_default_", 

        //register by object id or uid 
        //"condition": {"OBJECT":"4"}, 

        //register by classId 
        //"condition": {"CLASSID":3},    

        //register by object properties 
        //"condition": {"ATTRIBUTE":{"PropertyDict/sex":"male"}}, 

        //AND operator
        //"condition": {"AND":[{"PropertyDict/sex":"male"}, {"MoniterData/RealTimeData/status":"normal"}]}, 

        //OR operator 
        //"condition": {"OR":[{"PropertyDict/sex":"male"}, {"MoniterData/RealTimeData/status":"normal"}]}, 

        //NOT operator
        //"condition": {"NOT":{"AND":[{"PropertyDict/sex":"male"}, {"MoniterData/RealTimeData/status":"normal"}]}}, 

        //////////////////////////
        //condition shortcuts
        //a number，same as {"CLASSID":3}
        //"condition": 3, 

        //a string, means id or uid，same as {"OBJECT":"4"}
        //"condition": "4", 

        //a key/value pair，means object properties, same as {"ATTRIBUTE":{"PropertyDict/sex":"male"}}
        "condition": {"PropertyDict/sex":"male"}, 

        
        "event":"AddToSelection/callBack1",
        "priority":50,
        "cmds":[ 
            {    "cmd":"GetLastEventObj",  "toBuffer":{"ObjectManager":"RunBuffer/lastEventObj"} } , 
            {    "cmd":"ChangePlacementBundle",  "fromBuffer":{"ObjectManager":"RunBuffer/lastEventObj"} , "bundleId":"F933B1A524B94050BC7A82B15D2057F5"} 
        ]
    }

|

UnregEvent
^^^^^^^^^^^^

Unregister Event.

.. csv-table:: **Parameters**
    :header: Name,Required,Description
    :widths: 20,10,70

    id,No,Object id
    uid,No,Object uid(UserID)
    condition,No,Trigger condition
    event,Yes,"Same as  event parameter in :ref:`RegEvent <regevent-label>`

    .. note::
        if no callback is specified, all callbacks under this event will be unregistered.
    "

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "UnregEvent", 
        "condition":{
            "PropertyDict/sex":"male"
        }, 
        "event":"AddToSelection/callBack1" 
    }

|

GetLastEventObj
^^^^^^^^^^^^^^^^

Get object associated with event and save to buffer.


.. csv-table:: **Parameters**
    :header: Name,Required,Description
    :widths: 20,10,70

    toBuffer,Yes, "Target buffer

    .. note::
        object is save to ``{'ObjectManager':'RunBuffer/lastEventObj'}`` by system automatically
    "

**Example**

.. code-block:: json
    :linenos:

    {    
        "cmd":"GetLastEventObj",  
        "toBuffer":{
            "ObjectManager":"RunBuffer/lastEventObj"
        } 
    }

|


RegIgnoreEvent
^^^^^^^^^^^^^^^^

Suppress events.

.. csv-table:: **Parameters**
    :header: Name,Required,Description
    :widths: 20,10,70

    condition,Yes, "Same as condition parameter in :ref:`RegEvent <regevent-label>`"
    event,Yes,"Same as event parameter in :ref:`RegEvent <regevent-label>`

    .. note::
        if no callback is specified, all callbacks under this event will be suppressed.
     "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "RegIgnoreEvent", 
        "condition":"_default_", //suppress all AddToSelection events
        "event":"AddToSelection" 
    }

|

UnregIgnoreEvent
^^^^^^^^^^^^^^^^

Resume suppress events.

.. csv-table:: **Parameters**
    :header: Name,Required,Description
    :widths: 20,10,70

    condition,Yes, "Same as condition parameter in :ref:`RegEvent <regevent-label>`"
    event,Yes,"Same as event parameter in :ref:`RegEvent <regevent-label>`

    .. note::
        if no callback is specified, all callbacks under this event will be suppressed.
     "

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "UnregIgnoreEvent", 
        "condition":"_default_",
        "event":"AddToSelection" 
    }



