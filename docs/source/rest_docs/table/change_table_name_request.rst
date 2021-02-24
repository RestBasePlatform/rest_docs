ChangeLocalTableName Request
====================================


.. http:post:: /Table/

   This post request changes a local table name.

   .. note::

      You should specify one of: full table data(database, folder, table) or a local table name.

      **If defined both - full table data(database, folder, table) will be ignored.**


   **Example request**:

   .. sourcecode:: http

      POST /GrantTableAccess HTTP/1.1
      Host: example.com
      Accept: application/json

      [
        "table" : {
            "local_table_name": "some-loca-name"
        }, 
        "new_local_table_name": "some-new-name"
      ]

      OR 

      [
        "table" : {
            "database": "some-loca-name", 
            "folder": "some-folder", 
            "table": "some-table"
        }, 
        "new_local_table_name": "some-new-name"
      ]

   :reqheader admin_token: Admin token. 
   
   :query local_table_name: Local name of table.
   :query database: *part of full table path* Local name of table database.
   :query folder: *part of full table path* Folder name in a database where a table is located. 
   :query table: *part of full table path* Name of a table in folder.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
            "status": "success", 
            "new_table_name": "some-new-name"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 409: Table already exists. 
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check request body or headers.
   :statuscode 404: Error. Check error in a respsonse body.

