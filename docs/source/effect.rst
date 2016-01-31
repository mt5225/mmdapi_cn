Effect
=======

|

SetTransparency
^^^^^^^^^^^^^^^^

Set transparency of given object.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    trans,Yes,"Value range ``[0-1]``

     * 1: 100% transparent
     * 0: No transparency
    "

**Example**

* Set Object Transparency

.. code-block:: json
    :linenos:

    {
        "cmd": "SetTransparency", 
        "uid":"object01", 
        "trans":0.25 
    }

|

SetColor
^^^^^^^^^^^^^^^^

Set object color.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    color,Yes,"Color in RGB，for instance, red is ``[255, 0, 0]``"
    ratio,No,"Effect ratio, range from 0 to 1"

**Example**

* Set Object Color

.. code-block:: json
    :linenos:

    {
        "cmd": "SetColor",
         "uid":"object01",
         "color":[1,0,0],
         "ratio":0.75 
    }

|

Fade
^^^^^^^^^^^^^^^^

Fade effect.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    start,Yes,,"Start transparent value, range ``[0-1]``"
    end,Yes,,"End transparent value,  range ``[0-1]``"
    time,No,1,Effect duration in seconds
    endAutoRelease,No,``true``, if resume object status after effect end
    enable,No,``true``,  Enable fading effect


**Example**

* Fading Effect

.. code-block:: json
    :linenos:

    {
        "cmd": "Fade",
        "uid":"object01",
        "start":1.0,
        "end":0.0, 
        "time":1.0, 
        "endAutoRelease":true 
    }

* Disable Effect

.. code-block:: json
    :linenos:

    {
        "cmd": "Fade",
         "uid":"object01",
         "enable":false
     }

|

FadeIn
^^^^^^^

Fade In Effect.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    time,Yes,1,Effect duration in seconds.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "FadeIn",
        "uid":"object01",
        "time":1.0 
    }

|

FadeOut
^^^^^^^

Fade Out Effect.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    time,Yes,1,Effect duration in seconds.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "FadeOut",
        "uid":"object01",
        "time":1.0 
    }

|

Flash
^^^^^^^^^^^^^^^^

Flash effect.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    start,Yes,,Start transparent value
    end,Yes,,End transparent value
    time,No,1,Effect duration in seconds
    endAutoRelease,No,``true``, if resume object status after effect end
    enable,No,``true``,  Enable fading effect


**Example**

* Flash Effect

.. code-block:: json
    :linenos:

    {
        "cmd": "Flash",
        "uid":"object01",
        "start":1.0,
        "end":0.0, 
        "time":1.0, 
        "endAutoRelease":true 
    }

* Disable Flash

.. code-block:: json
    :linenos:

    {
        "cmd": "Flash",
        "uid":"object01",
        "enable":false
     }


|


ColorFade
^^^^^^^^^^^^^^^^

ColorFade effect.

.. csv-table:: **Parameters**
    :header: Name, Required,Default,Description
    :widths: 20,10,10,60

    :ref:`Object Reference <api-object-label>`,Yes,, Object Reference
    color,Yes,,Color used in effect
    start,Yes,,"Color density at the start, value range ``[0-1]``"
    end,Yes,,"Color density at the end, value range ``[0-1]``"
    time,No,1,Effect duration in seconds
    endAutoRelease,No,``true``, if resume object status after effect end
    enable,No,``true``, Enable fading effect


**Example**

* Change object to red in one second

.. code-block:: json
    :linenos:

    {
        "cmd": "ColorFade",
        "uid":"object01",
        "color":[1,0,0],
        "start":0.0,
        "end":1.0, 
        "time":1.0, 
        "endAutoRelease":false 
    }

* Disable Effect

.. code-block:: json
    :linenos:

    {
        "cmd": "ColorFade",
        "uid":"object01",
        "enable":false
     }








