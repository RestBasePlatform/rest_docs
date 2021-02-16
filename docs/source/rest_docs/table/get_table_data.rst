GetTableData Request
====================================

.. http:get:: /Table

   This post request returns database connection data (*except password*)

   **Example request**:

    .. sourcecode:: http

      GET /Table HTTP/1.1
      Host: example.com
      Accept: application/json
    
   :reqheader user_token: User token. 

   :query local_table_name: Local name of a table.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

    {
        "TableData": {
            "columns": {
                "column1": "timestamp without time zone",
                "column2": "text",
                "column3": "real",
            },
            "database_name": "local-database-name",
            "folder_name": "folder-name-in-database",
            "table_name": "table-name-in-database"
        },
        "status": "success"
    }

   :statuscode 200: No errors.
   :statuscode 403: Access denied. Check token in a header. 
   :statuscode 400: Bad request. Check request body or headers.
   :statuscode 404: Table not found
