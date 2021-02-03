GrantTableAccess Request
====================================


.. http:post:: /GrantTableAccess/(str:local_table_name)/(str:database)/(str:folder)/(str:table)

   This post request grants access to table for token. 

   .. note::

      You should specify one of parametrs full table data(database, folder, table) or a local table name.

      **If defined both - local table name will be ignored.**


   **Example request**:

   .. sourcecode:: http

      POST /GrantTableAccess HTTP/1.1
      Host: example.com
      Accept: application/json

   :reqheader admin_token: Admin token. 
   
   :query user_token: Token to grant access for.
   :query local_table_name: Local name of table.
   :query database: *part of full table path* Local name of table database.
   :query folder: *part of full table path* Folder name in a database where a table is located. 
   :query table: *part of full table path* Name of a table in folder.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: text/javascript

      [
        {
            "status": "success"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 409: Token already exists. 
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check request body.
   :statuscode 404: Error. Check error in a respsonse body.

