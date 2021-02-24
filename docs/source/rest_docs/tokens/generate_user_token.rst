GenerateUserToken Request
====================================


.. http:put:: /GenerateUserToken/

   This get request generates an user token for restbase-server.  

   **Example request**:

   .. sourcecode:: http

      PUT /GenerateUserToken HTTP/1.1
      Host: example.com
      Accept: application/json

   :reqheader admin_token: Admin token. 
   :query token_name: Name of token. Required for identification token in ListUserTokens request. 
   :query user_token: **Optional** Pre-defined user token. If ``user_token`` is not defined it will be generated automatically. 
   :query description: **Optional**  Token description.
   
   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
            "status" : "success"
            "new_token": "some-user-token"
        }
      ]

   :statuscode 201: No errors.
   :statuscode 409: Token already exists. 
   :statuscode 403: Access denied. Check admin token in a header. 
   :statuscode 400: Bad request. Check a request body or headers.
