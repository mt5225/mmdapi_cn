Buffer
======

CopyBuffer
^^^^^^^^^^^

Copy content of source buffer to target buffer, content in target buffer will be overwrote.

.. note::
    This command only apply to object buffers

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 6, 5, 20

    fromBuffer,Yes, source buffer path
    toBuffer,Yes, target buffer path



**Example**
  
* copy buffer by full path

.. code-block:: json
    :linenos:

    {
        "cmd": "CopyBuffer", 
        "fromBuffer":{"ObjectManager":"RunBuffer/buffer1"}, 
        "toBuffer":{"ObjectManager":"RunBuffer/buffer2"} 
    }


* copy buffer by relative path
  
.. code-block:: json
    :linenos:

    {
        "cmd": "CopyBuffer", 
        "fromBuffer":"buffer1", 
        "toBuffer":"buffer2" 
    }

**NOTE**

* ``buffer1`` same as  ``{"ObjectManager":"RunBuffer/buffer1"}``
* ``buffer2`` same as ``{"ObjectManager":"RunBuffer/buffer2"}``

|

MergeBuffer
^^^^^^^^^^^^

Copy content of source buffer to target buffer, content in target buffer will be reserved.

.. note::
    This command only apply to object buffers

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 6, 5, 20

    fromBuffer,Yes, source buffer path
    toBuffer,Yes, target buffer path

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "MergeBuffer", 
        "fromBuffer":{"ObjectManager":"RunBuffer/buffer1"}, 
        "toBuffer":{"ObjectManager":"RunBuffer/buffer2"} 
    }

|

SubtractBuffer
^^^^^^^^^^^^^^

Delete objects in target buffer which are identical to objects in source buffer.

.. note::
    This command only apply to object buffers

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 6, 5, 20

    fromBuffer,Yes, source buffer path
    toBuffer,Yes, target buffer path


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "SubtractBuffer", 
        "fromBuffer":{"ObjectManager":"RunBuffer/buffer1"}, 
        "toBuffer":{"ObjectManager":"RunBuffer/buffer2"} 
    }

|

SetObjectsToBuffer
^^^^^^^^^^^^^^^^^^^

Assign object to buffer.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 6, 5, 20

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference
    toBuffer,Yes, target buffer path



**Example**

* refer object by uid

.. code-block:: json
    :linenos:

    {
        "cmd": "SetObjectsToBuffer", 
        "uid":"obj01", 
        "toBuffer":{"ObjectManager":"RunBuffer/objsBuffer"} 
    }

* object uid list

.. code-block:: json
    :linenos:

    {
        "cmd": "SetObjectsToBuffer", 
        "uids":["obj01", "obj02"], 
        "toBuffer":{"ObjectManager":"RunBuffer/objsBuffer"} 
    }

* refer object by id

.. code-block:: json
    :linenos:

    {
        "cmd": "SetObjectsToBuffer", 
        "id":"dg23dvw41hrdve", 
        "toBuffer":{"ObjectManager":"RunBuffer/objsBuffer"} 
    }

|

SetBufferValue
^^^^^^^^^^^^^^^^

Assign value to buffer.

.. csv-table:: **Parameters**
    :header: Name, Required, Description
    :widths: 6, 5, 20

    toBuffer,Yes, target buffer path
    value,Yes, value to be set


**Example**

* empty buffer

.. code-block:: json
    :linenos:

    {
        "cmd": "SetBufferValue", 
        "toBuffer":{"ObjectManager":"RunBuffer/buffer1"}, 
        "value":""  
    }



