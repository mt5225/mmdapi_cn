Monitor
========

|

SetMonitorRespond
^^^^^^^^^^^^^^^^^^^^

Set response to MonitorDatas/RealTimeData.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    config,Yes, "Response is based on properties of MonitorDatas/RealTimeData.
    
    .. note::
        1. Support configure response on multiable properties
        2. Supports multiable response to single property.
        3. Value of property can be string or number. if property value are all numbers, system will sort those numbers and trigger command with equal or less than numbers.
        4. If property value are all strings, use '_default_' to run command if data is NOT in value set.
        5. Use GetLastMonitorRespondObj to get current object in callback, or use buffer: ``{'ObjectManager':'RunBuffer/lastMonitorRespondObj'}`` to get current object
    "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "SetMonitorRespond", 
        "fromBuffer":{"ObjectManager": "RunBuffer/Grain"},
        "config":{
            "GrainCatelog":{ //get value from "MonitorDatas/RealTimeData/GrainCatelog"
                "Corn":[ //run command if value is "Corn"
                    {"cmd": "GetLastMonitorRespondObj", "toBuffer":"monitorRespondObj"}, //run command
                    {"cmd": "ChangePlacementTexture", "fromBuffer":"monitorRespondObj", "url": "images/corn.jpg"}
                ],
                "Wheat":[ //run command if value is "Wheat"
                    {"cmd": "GetLastMonitorRespondObj", "toBuffer":"monitorRespondObj"}, //run command
                    {"cmd": "ChangePlacementTexture", "fromBuffer":"monitorRespondObj", "url": "images/wheat.jpg"}
                 ]
            },
            "GrainStorage":{ //get value from "MonitorDatas/RealTimeData/GrainStorage"
                "10":[{"cmd":"SetScale", "fromBuffer":"lastMonitorRespondObj", "scale":[1,0.1,1] } ], // run command if value equal or less than 10, note that current object is fetch by system buffer lastMonitorRespondObj
                "30":[{"cmd":"SetScale", "fromBuffer":"lastMonitorRespondObj", "scale":[1,0.3,1]  } ], //run command if value equal or less than 30 
                "50":[{"cmd":"SetScale", "fromBuffer":"lastMonitorRespondObj", "scale":[1,0.5,1]  } ], //run command if value equal or less than 50
                "80":[{"cmd":"SetScale", "fromBuffer":"lastMonitorRespondObj", "scale":[1,0.8,1]  } ], //run command if value equal or less than 50
                "100":[{"cmd":"SetScale", "fromBuffer":"lastMonitorRespondObj", "scale":[1,1,1]  } ] //run command if value equal or less than 100
            },
            "GrainStatus":{ //get value from "MonitorDatas/RealTimeData/GrainStatus"
                "InsectHazzard":[{"cmd":"ColorFlash",   "fromBuffer":"lastMonitorRespondObj",   "color":[1,0,0] , "start":0.6, "end":0.2, "time":1.0 } ], //run command if value equals to InsectHazzard
                "Decay":[{"cmd":"ColorFlash",   "fromBuffer":"lastMonitorRespondObj",   "color":[0,0,1] , "start":0.6, "end":0.2, "time":1.0 } ], //run command if value equals to Decay
                "_default_":[{"cmd":"ColorFlash",   "fromBuffer":"lastMonitorRespondObj",   "enable":false } ] //run command if no match
            }
        }
    }

|

GetLastMonitorRespondObj
^^^^^^^^^^^^^^^^^^^^^^^^^^

Get current object.


.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    toBuffer,Yes,Buffer name

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "GetLastMonitorRespondObj", 
        "toBuffer":"monitorRespondObj" 
    }



