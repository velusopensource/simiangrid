MoveInventoryNodes Method
=========================

Move a list of inventory nodes to a new folder.


Request Format
--------------

+-----------------+----------------------------------+----------+------------+
| *Parameter*     |  *Description*                   |  *Type*  | *Required* |
+=================+==================================+==========+============+
| `RequestMethod` | MoveInventoryNodes               | String   | Yes        |
+-----------------+----------------------------------+----------+------------+
| `OwnerID`       | UUID of the inventory owner      | UUID     | Yes        |
+-----------------+----------------------------------+----------+------------+
| `FolderID`      | UUID of the target folder        | UUID     | Yes        |
+-----------------+----------------------------------+----------+------------+
| `Items`         | Comma-separated list containing  | String   | Yes        |
|                 | UUIDs of the inventory nodes to  |          |            |
|                 | move                             |          |            |
+-----------------+----------------------------------+----------+------------+


Sample request: ::

    RequestMethod=MoveInventoryNodes
    &OwnerID=9ffd5a95-b8bd-4d91-bbed-ded4c80ba151
    &FolderID=944350b5-4228-4809-b201-b4bcb586bb53
    &Items=8ccf95f0-4dc1-48bf-ba77-881a196ff73f%2Ce40e137f-ea12-42e2-a863-d034cbc2c30b


Response Format
---------------

+-------------+--------------------------------------------+---------+
| *Parameter* | *Description*                              | *Type*  |
+=============+============================================+=========+
| `Success`   | True if the nodes were successfully moved, | Boolean |
|             | False if a Message was returned            |         | 
+-------------+--------------------------------------------+---------+
| `Message`   | Error message                              | String  | 
+-------------+--------------------------------------------+---------+


Success: ::


    {
        "Success":true
    }


Failure: ::


    {
        "Success":false,
        "Message":"Target folder does not exist"
    }

