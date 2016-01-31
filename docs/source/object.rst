.. _api-object-label:

Base Class：Object
=================================

Commands which inherits from ObjectCommand will have following methods build-in.

.. list-table:: **Parameters**
   :widths: 10 6 25
   :header-rows: 1

   * - Name
     - Required
     - Description
   * - **id**
     - No
     - Get object by ID
   * - **uid**
     - No
     - Get object by UID, e.g. user define ID
   * - **ids**
     - No
     - Get objects by ID array
   * - **uids**
     - No
     - Get objects by UID array
   * - **fromBuffer**
     - No
     - Get content from buffer, would be one or more objects, or command results
   * - **toBuffer**
     - No
     - Buffer to save command results