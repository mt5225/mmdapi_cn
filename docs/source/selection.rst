Selection
==========

|

AddToCandidate
^^^^^^^^^^^^^^^

Add objects to 'candidate set'.

.. note::
    Candidate set will be reset after scene switch


.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "AddToCandidate", 
        "uids": ["obj01", "obj02"] 
    }

|

ClearCandidate
^^^^^^^^^^^^^^^^

Empty candidate set.

.. note::
    Candidate set will be reset after scene switch.


**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ClearCandidate" 
    }

|

RemoveFromCandidate
^^^^^^^^^^^^^^^^^^^^^

Remove objects from candidate set.

.. note::
    Candidate set will be reset after scene switch


.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "RemoveFromCandidate", 
        "uids":["obj01, "obj02"] 
    }

|

AddToSelection
^^^^^^^^^^^^^^^^^^^^^

Add objects to 'selection set' and marked as 'selected'.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "AddToSelection", 
        "uids":["obj01", "obj02"] 
    }

|

ClearSelection
^^^^^^^^^^^^^^^^

Empty selection set and mark all objects as 'unselected'.

**Parameters**

No parameters.


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "ClearSelection" 
    }

|

RemoveFromSelection
^^^^^^^^^^^^^^^^^^^^^

Remove objects from selection set and mark as 'unselected'.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    :ref:`Object Reference <api-object-label>`,Yes, Object Reference


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "AddToSelection", 
        "uids":["obj01", "obj02"] 
    }

|

GetSelection
^^^^^^^^^^^^^^

Save objects in selection set to buffer

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    toBuffer,Yes,Buffer to save object

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "GetSelection", 
        "toBuffer":{"ObjectManager":"RunBuffer/selection"} 
    }

|

LockSelection
^^^^^^^^^^^^^^^^

Lock selection set, cannot remove or add new object if locked.

**Parameters**

No parameters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "LockSelection" 
    }

|

UnlockSelection
^^^^^^^^^^^^^^^^

UnlockSelection selection set.

**Parameters**

No parameters.

**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "UnlockSelection" 
    }

|

EnableRectangleSelect
^^^^^^^^^^^^^^^^^^^^^^^

Enable bulk selector in UI.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    enable,Yes,``True`` or ``False``


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "EnableRectangleSelect", 
        "enable":true 
    }

|

EnalbeCheckRectangleUpdate
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Update bulk selection in real-time, recommended value: ``false``

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,20,60

    enable,Yes,``True`` or ``False``


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "EnalbeCheckRectangleUpdate", 
        "enable":true 
    }

|

LimitRectangleSelectNum
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Limit number of selected objects by bulk selector.

.. csv-table:: **Parameters**
    :header: Name, Required,Description
    :widths: 20,10,70

    num,Yes, maxim number of selected objects by bulk selector


**Example**

.. code-block:: json
    :linenos:

    {
        "cmd": "LimitRectangleSelectNum", 
        "num": 4
    }

