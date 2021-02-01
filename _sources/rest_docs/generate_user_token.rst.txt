GenerateUserToken Request
====================================


.. http:get:: /GenerateUserToken/(str:user_token)

   This get request generates an admin token for restbase-server.  

   **Example request**:

   .. sourcecode:: http

      GET /GenerateUserToken HTTP/1.1
      Host: example.com
      Accept: application/json

   :reqheader admin_token: Admin token. 
   :query user_token: **Optional** Pre-defined user token. If ``user_token`` is not defined it will be generated automatically. 

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: text/javascript

      [
        {
            "status" : "success"
            "new_token": "some-user-token"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 409: Token already exists. 
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check a request body.