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

