ListDatabase Request
====================================

.. http:get:: /Database/list

   This get request list of databases in RestBase. (*except password*)

   **Example request**:

    .. sourcecode:: http

      GET /Database/List HTTP/1.1
      Host: example.com
      Accept: application/json
    
   :reqheader admin_token: Admin token. 

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      {
        "List": [
            "database-local-name-1",
            "database-local-name-2",
            "database-local-name-3",
            "database-local-name-4"
        ],
        "status": "success"
    }

   :statuscode 200: No errors.
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check request body.
   :statuscode 404: Database not found
