AddSession Method
=================

Creates a login session for a user.

Request Format
--------------

+-------------------+---------------------------------+---------+------------+
| *Parameter*       | *Description*                   | *Type*  | *Required* |
+===================+=================================+=========+============+
| `RequestMethod`   | AddSession                      | String  | Yes        | 
+-------------------+---------------------------------+---------+------------+
| `UserID`          | UUID of the user to create a    | UUID    | Yes        |
|                   | login session for               |         |            | 
+-------------------+---------------------------------+---------+------------+
| `SessionID`       | Identifier to use for this      | UUID    | Optional   |
|                   | session                         |         |            | 
+-------------------+---------------------------------+---------+------------+
| `SecureSessionID` | Secure identifier to use for    | UUID    | Optional   |
|                   | this session. Must only be      |         |            |
|                   | transmitted across secure       |         |            |
|                   | channels                        |         |            | 
+-------------------+---------------------------------+---------+------------+

  * If `SessionID` and `SecureSessionID` are not specified they will be randomly generated.
  * `LastLoginDate` in the user's account data is updated with the current timestamp.


Sample request: ::

    RequestMethod=AddSession
    &UserID=efb00dbb-d4ab-46dc-aebc-4ba83288c3c0


Response Format
---------------

+-------------------+----------------------------------------------+---------+
| *Parameter*       | *Description*                                | *Type*  |
+===================+==============================================+=========+
| `Success`         | True if session data was returned, False if  | Boolean |
|                   | a Message was returned                       |         | 
+-------------------+----------------------------------------------+---------+
| `SessionID`       | Current session identifier                   | UUID    | 
+-------------------+----------------------------------------------+---------+
| `SecureSessionID` | Current session identifier that must only be | UUID    |
|                   | transmitted across secure channels           |         | 
+-------------------+----------------------------------------------+---------+
| `Message`         | Error message                                | String  | 
+-------------------+----------------------------------------------+---------+

Success: ::


    {
        "Success":true,
        "SessionID":"23e8bfa6-2123-4499-9670-9fe537e3e1f7",
        "SecureSessionID":"905e167a-0330-4b5c-9a1e-f940e2925303"
    }


Failure: ::


    {
        "Success":false,
        "Message":"SessionID is already in use"
    }

