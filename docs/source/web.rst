Web
=====

OpenUrl
^^^^^^^^^

Open webpage, same as run javascript function window.open, only valid in browser.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    url,No, URL to be open
    urlBuffer,No,Get URL from urlBuffer
    param,No,"Same as parameters used in javascript function window.open
    for instance： ``height=100, width=400, toolbar =no, menubar=no, scrollbars=no, resizable=no, location=no, status=no``

    "


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "OpenUrl", 
        "url":"http://www.3dmomoda.com", 
        "param": "height=100, width=400, toolbar =no, menubar=no, scrollbars=no, resizable=no, location=no, status=no"
    }

.. code-block:: json
    :linenos:

    {
        "cmd": "OpenUrl", 
        "urlBuffer":"url", 
        "param": "height=100, width=400, toolbar =no, menubar=no, scrollbars=no, resizable=no, location=no, status=no"
    }

|

UrlWindow
^^^^^^^^^^

Open browser window with given URL, only valid in browser.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    url,No, URL to be open
    urlBuffer,No,Get URL from urlBuffer
    title,No,Window title
    titleBuffer,No,Get window title from buffer
    width,No,Window width
    height,No,Window height


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "UrlWindow", 
        "urlBuffer":"url", 
        "title": "message", 
        "width": 512, 
        "height": 512 
    }

|

HtmlWindow
^^^^^^^^^^

Open browser windows and display given html, only valid in browser.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    html,No,Data in html format
    htmlBuffer,No,Get html data from urlBuffer
    title,No,Window title
    titleBuffer,No,Get window title from buffer
    width,No,Window width
    height,No,Window height


**Example**

* Display HTML

.. code-block:: json
    :linenos:

    {
        "cmd": "HtmlWindow", 
        "html": "<ol><li>dog</li><li>cat</li><li>bird</li></ol>", 
        "title": "Catalog", 
        "width": 512, 
        "height": 512 
    }

* Display HTML from buffer

.. code-block:: json
    :linenos:

    {
        "cmd": "HtmlWindow", 
        "htmlBuffer":{"ObjectManager":"RunBuffer/htmlContent"}, 
        "title": "Catalog", 
        "width": 512, 
        "height": 512 
    }

|

HideWindow
^^^^^^^^^^^^^^^^^^^^^^^

Close window opened by UrlWindow or HtmlWindow, only valid in browser.

**Parameters**

No Parameters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "HideWindow" 
    }

|

ExecuteHtmlInterface
^^^^^^^^^^^^^^^^^^^^^^

Open browser windows and display given html, only valid in browser.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 20,10,70

    interfaceName,No,javascript method name
    fromBuffer,No,"Set buffer content(object only) to javascript method

    .. note::
        #. Data structure pass to javascript method
        
            .. code-block:: javascript
                :linenos:

                {
                    'ID':'J17gKNmUeUeSXpDzPH_pZA', //ObjecID'
                    'UserID':'100007001', //Object UID'
                    'Name':'Box002', //Object name'
                    'ParentObjectUserID':'floor001', //Parent Object UID'
                    'ParentObjectID':'144', //Parent Object ID'
                    'Position':'-21.263 2.357 -5.653', //Coordinate in world'
                    'LocalPosition':'-22.944 2.357 -10.038', //Coordinate in Parent'
                    'BoundBoxMax':'-21.163 2.657 -5.630', //Object bound point (max)'
                    'BoundBoxMin':'-21.363 2.357 -5.675', //Object bound point (min)'
                    'BundleId':'B723E9E1B279467EBC9433D30D35F683', //Model ID'
                    'BundleSize':'1.000 1.000 1.000', //Model size'
                    'BundleVersion':'1.000 1.000 1.000', //Model version'
                    'BundleTitleEn':'Universal side box', //Model name in english'
                    'BundleTitle':'Universal side box', //Model name'
                    'PropertyDict':{'ObjectType':'box'}, //User-define properties'
                    'MonitorDatas/RealTimeData':{'Temperature':67} //Monitoring data'
                }
                
        #. Use exArguments to pass additional values
        
    "
    exArguments,No,Additional arguments in array

**Example**

.. code-block:: javascript
    :linenos:

    //////////////////////////////////////////////////////////
    //Pass object from buffer to javascript method
    //////////////////////////////////////////////////////////

    //define method in javascript
    var keeper = {};
    keeper.getSelectedObjs = function(objs){
        objs = mmd.jsonTools.parseJSON(objs);
        for(var i = 0 ; i < objs.length; i++){
            ......
        }
    }

    //call method
    {
        "cmd": "ExecuteHtmlInterface", 
        "interfaceName": "keeper.getSelectedObjs", 
        "fromBuffer":{"ObjectManager":"RunBuffer/selection"} 
    }

    //////////////////////////////////////////////////////////
    //Pass object from buffer to javascript method with additional arguments
    //////////////////////////////////////////////////////////

    //define javascript method
    var keeper = {};
    keeper.setColorByType = function( objs, objType, color ){
        objs = mmd.jsonTools.parseJSON(objs);
        var uids = [];
        for(var i = 0 ; i < objs.length; i++){
            var obj = objs[i];
            if(obj["PropertyDict"]["ObjectType"] == objType){
                uids.push(obj["UserID"]);
            }
        };
        var cmds = [
            { "cmd":"SetColor", "uids":uids, "color":color}
        ];
        var cmdsStr = mmd.jsonTools.toJSON(cmds);
        mmd.RunCommand( cmdsStr, true);
    }

    //call method
    {
        "cmd": "ExecuteHtmlInterface", 
        "interfaceName": "keeper.setColorByType", 
        "fromBuffer":{"ObjectManager":"RunBuffer/objs"}, 
        "exArguments":[ "100box", [1,0,0]]
    }

    //////////////////////////////////////////////////////////
    //Pass arguments without object data
    //////////////////////////////////////////////////////////

    //define javascript method
    var saveLog = function( text, sync ){
        ......
    }

    //call method
    {
        "cmd": "ExecuteHtmlInterface", 
        "interfaceName": "saveLog", 
        "exArguments":[ "scene is open", false]
    }















