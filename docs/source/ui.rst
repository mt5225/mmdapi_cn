UI
===

|

ShowPanel
^^^^^^^^^^^

Show or hide setting panel.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    panel,Yes,"Name of the panel, can be one of: 

    * viewPointPanel： Viewpoint Panel
    * fuctionListPanel： Function List Panel
    * switch3dPanel： 2D-3D Switch Panel
    * effectPanel： Effect Panel
    * screenShotPanel： ScreenShot Panel
    * levelPanel： Floor Panel

    "
    enable,Yes, Show or hide panel

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ShowPanel", 
        "panel":"viewPointPanel", 
        "enable":false 
    }

|

CreatePlacemarkTemplate
^^^^^^^^^^^^^^^^^^^^^^^^^

Create new UI panel.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    template,Yes,"Panel settings, see below sample code for details"

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "CreatePlacemarkTemplate", 
        "template":{ 
            "name": "Template Example",

            //panel size
            "bgWidth": 243,
            "bgHeight": 149,

            //position of panel axis
            "horizontalAlignment":"LEFT",    // horizontal position, can be one of LEFT CENTER RIGHT
            "verticalAlignment":"TOP",    // vertical position, can be one of TOP CENTER BOTTOM

            //controls included in panel
            "showMapping": {
                "Background": {
                    //parameters
                    "type": "image",
                    "sortOrder": 0,
                    "drawPos": [0, 0],
                    "drawSize": [ 243, 149 ],
                    
                    //control axis position
                    "horizontalAlignment":"LEFT",    //horizontal position, can be one of LEFT CENTER RIGHT
                    "horizontalAlignmentOffset":0,    //horizontal offset
                    "verticalAlignment":"TOP",    //vertical position, can be one of TOP CENTER BOTTOM
                    "verticalAlignmentOffset":0,    //vertical offset
                    
                    //private parameters
                    "image":"userimage/4815/CustomTexture/20151023824126.png",
                    "color":[0,0,1],    //color settings may mix with image 
                    
                    //data source settings
                    "getMethod": "objectPropertyMapping",
                    "propertyPath":"MonitorDatas/RealTimeData/status",
                    "objectPropertyMapping":{
                        "_default_":"userimage/4815/CustomTexture/1.png",    //image location
                        "alarms":{"color":[1,0.2,0.2]},    //change color
                        "error":{    //change color and texture at the same time
                            "image":"userimage/4815/CustomTexture/3.png",
                            "color":[1,0,0]
                        }
                    }
            },
            "name": {
                    //parameters
                    "type": "text",
                    "sortOrder": 1,
                    "drawPos": [0, 0],
                    "drawSize": [243, 39],
                    
                    //axis position
                    "horizontalAlignment":"LEFT",    //horizontal position, can be one of LEFT CENTER RIGHT
                    "horizontalAlignmentOffset":0,    //horizontal offset
                    "verticalAlignment":"TOP",    //vertical position, can be one of TOP CENTER BOTTOM
                    "verticalAlignmentOffset":0,    //vertical offset
                    
                    //private  parameters
                    "fontFamily": "Arial",    //font family
                    "fontSize": 14,
                    "fontColor": [1,1,1,1],
                    "fontStyle": "Bold",
                    "fontShadow": false,
                    "fontShadowThickness": 2,
                    "fontShadowColour": [0,0,0],
                    "fontShadowOffset": [2, 2],
                    "fontOutline": true,
                    "fontOutlineThickness": 2,
                    "horizontalOverflow": false,
                    "verticalOverflow": true,
                    "fontOutlineColour": [0,0,0],
                    
                    "horizontalTextAlignment": "CENTER",
                    "verticalTextAlignment": "CENTER",
                    "horizontalWriterAlignment": "TOP",
                    "verticalWriterAlignment": "LEFT",
                    
                    //data source
                    "getMethod": "objectProperty",
                    "propertyPath": "UserID"
                },
                "status": {
                    //control parameters
                    "type": "text",
                    "sortOrder": 1,
                    "drawPos": [26,80],
                    "drawSize": [50,30],
                    
                    //control private paramters, list only common ones
                    "fontSize": 14,
                    "fontColor": [1,1,1,1],
                    
                    //data source
                    "getMethod": "objectPropertyMapping",
                    "propertyPath": "MonitorDatas/RealTimeData/status",
                    "objectPropertyMapping":{
                        "_default_":{"text":"Normal", "fontColor":[0,1,0]},
                        "false":{"text": "Error", "fontColor":[1,0,0]}
                    }
                },        
                 "progressBar": {
                    //parameters
                    "type": "progressBar",
                    "sortOrder": 1,
                    "drawPos": [74, 40],
                    "drawSize": [128, 20],
                    
                    //axis position
                    "horizontalAlignment":"LEFT",    //horizontal position, can be one of LEFT CENTER RIGHT
                    "horizontalAlignmentOffset":0,    //horizontal offset
                    "verticalAlignment":"TOP",    //vertical position, can be one of TOP CENTER BOTTOM
                    "verticalAlignmentOffset":0,    //vertical offset
                    
                    //private parameters
                    "fillDir": "right",    //"up" "down" "left" "right"
                    "barImage":"uGUI/ProgressBar/img_0",
                    "min": 20,
                    "max": 30,
                    "color": [0.513,0.874,0.552,1],
                    "styleConfig": {
                        "0.25": [0.36,0.58,0.16],
                        "0.50": [1,0.83,0.4],
                        "0.75": [1,0.4,0],
                        "0.90": [1,0.15,0.15]
                    },
                    
                    //data source
                    "getMethod": "objectProperty",
                    "propertyPath": "MonitorDatas/RealTimeData/humidity"
                },
                "pieChart": {
                    //parameters
                    "type": "progressPie",
                    "sortOrder": 1,
                    "drawPos": [99,90],
                    "drawSize": [50,50],
                    
                    //axis position
                    "horizontalAlignment":"LEFT",    //horizontal position, can be one of LEFT CENTER RIGHT
                    "horizontalAlignmentOffset":0,    //horizontal offset
                    "verticalAlignment":"TOP",    //vertical position, can be one of TOP CENTER BOTTOM
                    "verticalAlignmentOffset":0,    //vertical offset
                    
                    //private parameters
                    "openAngle":"360",
                    "fillDirClockwise":true,    //clockwise
                    "ringImage":"uGUI/ProgressBar/img_3",    //image path
                    "rotation":0,
                    "min": 20,
                    "max": 30,
                    "color": [0.513,0.874,0.552,1],
                    "styleConfig": {
                        "0.25": [0.36,0.58,0.16],
                        "0.50": [1,0.83,0.4],
                        "0.75": [1,0.4,0],
                        "0.90": [1,0.15,0.15]
                    },    
                    
                    //data source
                    "getMethod": "objectProperty",
                    "propertyPath": "MonitorDatas/RealTimeData/humidity"
                 
                },
                "ringChart": {
                    //parameters
                    "type": "progressRing",
                    "sortOrder": 1,
                    "drawPos": [149,90],
                    "drawSize": [50,50],
                    
                    //axis
                    "verticalAlignment":"CENTER",
                    "verticalAlignmentOffset":0,
                    "horizontalAlignment":"CENTER",
                    "horizontalAlignmentOffset":0,
                    
                    //private control
                    "openAngle":"360",
                    "fillDirClockwise":false,    // counter clockwise 
                    "ringImage":"uGUI/ProgressBar/img_2",    //image path
                    "rotation":0,
                    "min": 20,
                    "max": 30,
                    "color": [0.513,0.874,0.552,1],
                    "styleConfig": {
                        "0.25": [0.36,0.58,0.16],
                        "0.50": [1,0.83,0.4],
                        "0.75": [1,0.4,0],
                        "0.90": [1,0.15,0.15]
                    },    
                    
                    //data source
                    "getMethod": "objectProperty",
                    "propertyPath": "MonitorDatas/RealTimeData/humidity",
                },
                "DisplyValue": {
                    //parameters
                    "type": "text",    
                    "sortOrder": 2,
                    "drawPos": [74,65],
                    "drawSize": [128,20],
                    
                   //data source
                    "getMethod": "objectProperty",
                    "propertyPath": "MonitorDatas/RealTimeData/humidity"
                },
                "Button": {
                    //parameters
                    "type": "button",
                    "sortOrder": 1,
                    "drawPos": [194,98],
                    "drawSize": [35,22],
                    
                    //private parameters
                    "fontSize": 12,    
                    "fontColor": [0.235,0.792,0.501,1],
                    "title":"Details",
                    "normalColor": [0.3,0.5,0.3,0],
                    "highlightedColor": [1,1,1],
                    "pressedColor": [0.6,0.5,0.2,0],
                    
                    "cmds":[
                        {"cmd":"OpenUrl", "uid":{"objectManager":"Runbuffer/Button1"} }
                    ],
                    "cmdsImmediate":false
                },
                "SwitchButton": {
                    //parameters
                    "type": "toggle",
                     "sortOrder": 1,
                    "drawPos": [194,98],
                    "drawSize": [35,22],
                    
                    //private parameters
                    "images":["http://www.3momoda.com/images/add_01.png","images/add_02.png","images/add_02.png"],    //images use for normal, mouse over and mouse leave events. image url can be absolute，or relative to mmd server url
                    "fontSize": 12,    
                    "fontColor": [0.235,0.792,0.501,1],
                    "title":"Open",
                    "checked":true,
                    "setCheckedExe":false,    //if run command while checked
                    
                    "checkCmds":[
                        { "cmd":"SetPlacemarkProperty","uid":"obj01" ,"templateName":"Template" ,"widgetName":"SwitchButton" ,"property":"title" ,"value":"Close" }
                    ],
                    "unCheckCmds":[
                        { "cmd":"SetPlacemarkProperty","uid":"obj01" ,"templateName":"Template" ,"widgetName":"SwitchButton" ,"property":"title" ,"value":"开" }
                    ],    
                    "cmdsImmediate":false
                }
            }
        }
    }

|

CopyPlacemarkTemplate
^^^^^^^^^^^^^^^^^^^^^^^

Create new control by clone existing one.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    originName,Yes,The control panel to be cloned
    newName,Yes,Name of new control panel


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "CopyPlacemarkTemplate", 
        "originName":"Temperatureplacemark", 
        "newName":"Powerplacemark" 
    }

|

DestroyPlacemarkTemplate
^^^^^^^^^^^^^^^^^^^^^^^^^^

Delete Control.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    name,Yes,Name of Control to be deleted.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "DestroyPlacemarkTemplate", 
        "name":"Temperatureplacemark" 
    }

|

SetPlacemarkTemplateConfig
^^^^^^^^^^^^^^^^^^^^^^^^^^

Modify Control configuration.

.. note::
    this command will not modify look and feel of the control, to change control look and feel, please use command 'SetPlacemarkProperty'.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    name,Yes,Name of Control to be deleted.
    path,Yes,"List of properties to be modified, seperated by '/'"
    config,Yes,Target value


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SetPlacemarkTemplateConfig", 
        "name":"MonitoringPanel",
        "path":"ProgressBar2/styleConfig",
        "config":{
            "0.25":[0.36,0.58,0.16],
            "0.50":[1,0.83,0.4],
            "0.75":[1,0.4,0],
            "0.90":[1,0.15,0.15]
        }
    }

|

CreatePlacemark
^^^^^^^^^^^^^^^^^^^^^^^^^^

Placemark Creator.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    templateName,Yes,,Name of the placemark template
    placemarkId,No,, "Name of the placemark

    .. note::

        if placemark is created on the surface of object, placemarkId can be ignored. system will generate placemakrkId automatically using name conversion: ``{Object uid}_{Template Name}``
    "
    type,No,Screen,"coordinate type of UI, can of one of:
        * Screen：Placemark is created under screen coordinate, so it will not change during camera zoom in/zoom out
        * Plane：Placemark is created under 3D coordinate, so it could changes sizes with movement of camera
    "
    scale,No,"[0.2,0.2,0.2]","placemark scale, used to control sizes of placemark"
    presetPos,No,,"placemark position. if placemark type is 'Plane', use (x,y,z) as coordinate, if placemark type is 'screen'， use (x,y) as coordinate.

    .. note::
        if 'presetPos' is not specified, and placemark is created against object, the placemark is located on the top of the object by default.
    "
    posFromBuffer,No,,"Same as presetPos，set placemark position by buffer"
    layoutOffset,No,,"offset from target object, if placemark type is 'Plane', use (x,y,z) as coordinate, if placemark type is 'screen'， use (x,y) as coordinate."
    turnWhenNegative,No,,"Apply to (x,y) coordinate
    
    * if turnWhenNegative=true，coordinate is calculated as opposite, for instance, [-0.1, -100] point to position with right 10%, 100 pixels below
    * if turnWhenNegative=false，coordinate is located outside the screen. for instance, [-0.1, -100]point to position left -10%, up -100 pixels
    
    "
    countPerFrame,No,,Number of placemark object can be shown simultaneously
    additiveDataObjects,No,,"While placemark is created against object, target object be used as data source. If placemark need multiple data source , or not created against object, this parameter can be used to specifiy data source can be key-value, id, uid or buffer"
    updateTime,No,1,"Data refresh interval in seconds, if placemark is linked to external data source"


**Example**

* Create a monitoring panel to an object without placemarkId

.. code-block:: json
    :linenos:

    {
        "cmd": "CreatePlacemark", 
        "uid":"senser01", 
        "type":"Plane", 
        "templateName":"T&H Template", 
        "layoutOffset":[0,1,0],
        "scale":[0.1,0.1,0.1]
    }

* Create monitoring panel to multiple objects

.. code-block:: json
    :linenos:

    {
        "cmd": "CreatePlacemark", 
        "fromBuffer":"allSenser", 
        "type":"Screen", 
        "templateName":"T&H Panel", 
        "layoutOffset":[0,50],
        "countPerFrame":5
    }

* Create 2D placemark with multiple data source

.. code-block:: javascript
    :linenos:

    {
        "cmd": "CreatePlacemark", 
        "placemarkId":"Monitor01", 
        "type":"Screen", 
        "templateName":"MonitorPanel", 
        "presetPos":[0.5,50],
        "additiveDataObjects":{
            "ds1": "obj01" , //object id or uid
            "ds2": {"ObjectManager": "RunBuffer/obj02"} //use buffer as data source
        } 
    }

|

DestroyPlacemark
^^^^^^^^^^^^^^^^^

Destroy Placemark.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes,Object Reference
    placemarkId,No,placemarkId
    templateName,No,"If no placemarkId is specified while placemark is created, use ``{object uid}_{template name}`` as placemarkId，so templateName is need to delete placemark"

**Example**

* use object id and template name to destroy placemark

.. code-block:: json
    :linenos:

    {
        "cmd": "DestroyPlacemark", 
        "uid":"obj01", 
        "templateName":"T&H Panel"
    }

* use templateName to bulk delete placemark

.. code-block:: json
    :linenos:

    {
        "cmd": "DestroyPlacemark", 
        "fromBuffer":"allSenser", 
        "templateName":"T&H Panel Template"
    }

* use placemarkId to delete placemark

.. code-block:: json
    :linenos:

    {
        "cmd": "DestroyPlacemark", 
        "placemarkId":"TH01" 
    }

|

GetLastClickedButtonPlacemarkHost
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Simular to GetLastEventObj and GetLastMonitorRespondObj，click on placemark will return object reference.


.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    toBuffer,Yes,buffer which store the object


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "GetLastClickedButtonPlacemarkHost", 
        "toBuffer":"lastPlacemarkHost" 
    }

|

SetPlacemarkProperty
^^^^^^^^^^^^^^^^^^^^^

Modify property of existing placemark.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes,Object Reference
    placemarkId,No,Must specify placemarkId if placemark is created with placemarkId
    templateName,No,"TemplateName, note that if placemark is created without placemarkId, system will use ``{object_uid}_{template name}`` as placemarkId"
    widgetName,Yes,Control name
    property,Yes,Control property name
    value,Yes,"""Value to be modified.

    .. note::
        system use strong type internally. String, number or boolean can be used as normal, for other data type, the name of data type need to be specified. for instance, vector3，color should be wrote as:
          
         *  ``{Vector3:[1,0,0]}``
         *  ``{Vector2:[1,0]}``
         *  ``{Color:[1,0,0,1]}``

    """
    

**Example**

* String, number or boolean used as normal

.. code-block:: json
    :linenos:

    {
        "cmd": "SetPlacemarkProperty", 
        "uid":"obj01", 
        "templateName":"T&H Panel", 
        "widgetName":"Status", 
        "property":"text", 
        "value":"Normal" 
    }

* Specify data type if data type is vector3，color, etc.

.. code-block:: json
    :linenos:

    {
        "cmd": "SetPlacemarkProperty", 
        "uid":"obj01", 
        "templateName":"T&H Panel", 
        "widgetName":"Progressbar2", 
        "property":"Color", 
        "value":{"Color":[1,0,0]} 
    }




CreateLayerPanel
^^^^^^^^^^^^^^^^^

A build-in, easy to use, multi-function Panel provided by system.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    config,Yes,config
    presetPos,No, "Position, use (x,y) as coordinate

    .. note::
        default position is on top of object.
    "
    posFromBuffer,No,"Same as presetPos，set position from buffer"
    turnWhenNegative,No,"Apply to (x,y) coordinate

    * if turnWhenNegative=true，coordinate is calculated as opposite, for instance, [-0.1, -100] point to position with right 10%, 100 pixels below
    
    * if turnWhenNegative=false，coordinate is located outside the screen. for instance, [-0.1, -100]point to position left -10%, up -100 pixels
    "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "CreateLayerPanel", 
        "presetPos":[-100, 0.5],
        "turnWhenNegative":true,
        "config":{
            //set panel size
            "bgWidth": 150,
            "bgHeight": 330,

            //function groups
            "groups":[
                {
                    "name":"basic function",
                    "icon":"userimage/3534/CustomTexture/20150708325991.png", //icon path
                    "textConfig":{    //set text
                        "fontFamily": "Arial",
                        "fontSize": 18,
                        "drawSize": [100,38],
                        "verticalTextAlignment": "CENTER",
                        "fontColor": [1,1,1,1] 
                    },

                    //multiable functions inside one function group
                    "items":[
                        {
                             "name":"warehouse_index",
                             "textConfig":{    
                                 "fontFamily": "Arial",
                                 "fontSize": 14,
                                 "fontColor": [0,0,0,1]
                             },
                             "initCmds":[ //run command after creation
                                { "cmd":"ChangeLayerPanelItems","items":["warehouse_index"],"state":true } //set status as checked
                             ],
                             "checkCmds":[ //run command if checked
                                { "cmd":"ChangeLayerPanelItems","items":["TemperatureControl","humidityControl"],"state":false }, //uncheck other items
                                { "cmd":"CreatePlacemark", "fromBuffer":{"ObjectManager": "RunBuffer/warehouse"}, "templateName" : "warehouse_index", "type":"screen", "countPerFrame":100000}    
                             ],
                             "unCheckCmds":[ //run command if unchecked
                                { "cmd":"DestroyPlacemark", "fromBuffer":{"ObjectManager": "RunBuffer/warehouse"}, "templateName" : "warehouse_index"}
                             ]
                         },
                        {
                             "name":"temperature monitoring",
                            //......
                        },
                        //......
                    ]
                },
                {
                    "name":"advance settings",
                    //......
                },
                //......
            ]
        } 
    }

|

DestroyLayerPanel
^^^^^^^^^^^^^^^^^^^

Destroy Layer Panel.


**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "DestroyLayerPanel" 
    }

|

ChangeLayerPanelItems
^^^^^^^^^^^^^^^^^^^^^^^

Check or uncheck panel item.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    items,Yes,Set check status by array
    state,Yes,"``true`` means check, ``false`` means uncheck"


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ChangeLayerPanelItems", 
        "items":["Temperature Monitoring","Power Monitoring"], 
        "state":true 
    }

|

ShowLayerPanel
^^^^^^^^^^^^^^^^^^^^^^^

Show or hide Panel.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    enable,Yes,Panel name

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ChangeLayerPanelItems", 
        "items":["temperature monitoring","power monitoring"], 
        "enable":true 
    }

|

ShowHideLayerPanel
^^^^^^^^^^^^^^^^^^^

 Show or hide panel.


**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ShowHideLayerPanel" 
    }

|

ShowPropListPanel
^^^^^^^^^^^^^^^^^^^

A build-in, easy to use 'object property panel', can be also used to config function buttons.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    config,Yes,"Panel position, use (x,y) as coordinate.

    .. note::
        Default position is on top of object.
    "
    posFromBuffer,No, "Same as presetPos，set position from buffer"
    turnWhenNegative, No,"Apply to (x,y) coordinate

    * if turnWhenNegative=true，coordinate is calculated as opposite, for instance, [-0.1, -100] point to position with right 10%, 100 pixels below
    
    * if turnWhenNegative=false，coordinate is located outside the screen. for instance, [-0.1, -100]point to position left -10%, up -100 pixels
    
    "

**Example**

.. code-block:: javascript
    :linenos:

    {
        "cmd": "ShowPropListPanel", 
        "fromBuffer":{"ObjectManager": "RunBuffer/lastEventObj"},
        "presetPos":[100, 0.5],
        "turnWhenNegative":true,
        "config":{ 
            "initCmds":[ //run command after creation
                { "cmd":"CopyBuffer",  "fromBuffer":{"ObjectManager":"RunBuffer/lastEventObj"}, "toBuffer":{"ObjectManager":"RunBuffer/curShowPanelObj"}} ,
                { "cmd":"ChangePropListPanelItems", "items":["basicInfo"], "state":true, "exeCommands":true } //set which button is clicked after creation
            ],
            "items":[
                {
                    "name":"basicInfo",
                    "normalColor":[0.415,0.839,0.462,1],//color on normal status
                    "highlightedColor":[0.337,0.666,0.372,1], //color on mouse over
                    "pressedColor":[0.415,0.839,0.462,1], //color on mouse click
                    "clickCmds":[
                        { "cmd": "ChangePropListPanelItems", "items":["warehouseInfo","alarmInfo"], "state":false, "exeCommands":false},//uncheck other function button.
                        { "cmd": "GetValue", "fromBuffer":{"ObjectManager":"RunBuffer/curShowPanelObj"}, "path":"MonitorDatas/RealTimeData", "toBuffer":{"ObjectManager":"RunBuffer/panelData"}},
                        { "cmd": "SetPropListPanelKeyValue", "valueBuffer":{"ObjectManager":"RunBuffer/panelData"} ,"names":["warehouse_index","Catelog","Qualtity","Manager","UpdateTime","Power Consumption","CheckNumber"]}
                    ]
                },
                {
                    "name":"Warehouse Info",
                    "clickCmds":[
                        { "cmd": "ChangePropListPanelItems", "items":["basicInfo","alarmInfo"], "state":false, "exeCommands":false},
                        { "cmd": "GetValue", "fromBuffer":{"ObjectManager":"RunBuffer/curShowPanelObj"}, "path":"MonitorDatas/RealTimeData", "toBuffer":{"ObjectManager":"RunBuffer/panelData"}},
                        { "cmd": "SetPropListPanelKeyValue", "valueBuffer":{"ObjectManager":"RunBuffer/panelData"} ,"names":["Temperature","WarehouseTemperature","          Up","          MiddleUp","          MiddleDown","          Down","AvgTemperature","Humidity","InsectControl"]}
                    ]
                },
                {
                    "name":"alarmInfo",
                    "clickCmds":[
                        { "cmd": "ChangePropListPanelItems", "items":["basicInfo","warehouseInfo"], "state":"unclicked", "exeCommands":false},
                        { "cmd": "GetValue", "fromBuffer":{"ObjectManager":"RunBuffer/curShowPanelObj"}, "path":"MonitorDatas/RealTimeData", "toBuffer":{"ObjectManager":"RunBuffer/panelData"}},
                        { "cmd": "SetPropListPanelKeyValue", "valueBuffer":{"ObjectManager":"RunBuffer/panelData"} ,"names":["Temperature","Fire","InsectControl"]}
                    ]
                },
                {
                    "name":"Barcode",
                    "clickCmds":[
                        { "cmd": "GetValue", "fromBuffer":{"ObjectManager":"RunBuffer/curShowPanelObj"}, "path":"MonitorDatas/RealTimeData/barcode_url", "toBuffer":{"ObjectManager":"RunBuffer/barcode_url"}},
                        { "cmd": "UrlWindow" ,"urlBuffer":{"ObjectManager":"RunBuffer/barcode_url"} ,"title":"Barcode", "width":"250" , "height":"250"}
                    ]
                }
            ]
        }
    }

|

HidePropListPanel
^^^^^^^^^^^^^^^^^^^

Hide property list panel.


**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "HidePropListPanel" 
    }

|

ChangePropListPanelItems
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Change panel button status.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    items,Yes,Array to set button status in bulk
    state,Yes,"``ture`` means clicked, ``false`` means unclicked"
    exeCommands,No,Run command while state changed to clicked

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ChangePropListPanelItems", 
        "items":["warehouseInfo","alarmInfo"], 
        "state":false, 
        "exeCommands":false 
    }

|

SetPropListPanelKeyValue
^^^^^^^^^^^^^^^^^^^^^^^^^

Show object property on panel.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    valueBuffer,Yes,Buffer name
    names,No,Get data from buffer by order of name array


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SetPropListPanelKeyValue", 
        "valueBuffer":{"ObjectManager":"RunBuffer/panelData"}, 
        "names":["Temperature","Fire","InsectControl"] 
    }









