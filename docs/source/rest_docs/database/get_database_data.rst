GetDatabaseData Request
====================================

.. http:get:: /Database

   This get request returns database connection data (*except password*)

   **Example request**:

    .. sourcecode:: http

      GET /Database HTTP/1.1
      Host: example.com
      Accept: application/json
    
   :reqheader admin_token: Admin token. 

   :query local_database_name: Local name of a database.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
            "status": "success", 
            "ip": "localhost", 
            "port": "1234", 
            "username": "user", 
            "local_name": "local_database_name"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check request body.
   :statuscode 404: Database not found
