AddDatabase Request
====================================

.. http:put:: /Database

   This put request adds a new database(includes tables/folders) to API.

   .. note::

      RestBase has the same read privileges as an account.

   **Example request**:

   .. sourcecode:: http

      PUT /Database HTTP/1.1
      Host: example.com
      Accept: application/json
    
   :reqheader admin_token: Admin token. 
   
   :query local_database_name: Local database name in RestBase. This name uses in all full paths to a database. 
   :query ip: Database address **without port*.
   :query port: Database port.
   :query database: Database name on server.
   :query username: Database username.
   :query password: Password of the user from a `username` field.
   :query base_type: Database type. Supported values: 'postgres'

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
            "status": "success", 
            "local_name": "some-local-database-name"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check request body or headers.
   :statuscode 500: Error. Check error in a respsonse body.
