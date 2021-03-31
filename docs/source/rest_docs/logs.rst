Logs Request
====================================


.. http:get:: /Logs/

   This get request returns server logs.

   **Example request**:

   .. sourcecode:: http

      PUT /Logs HTTP/1.1
      Host: example.com
      Accept: application/json

   :reqheader admin_token: Admin token. 
   :query level: **Optional** Logging leve. One of `degug`, `info`, `error`. 

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      [
        {
            "status" : "success"
            "logs": "some-user-token"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 400: Bad request. Check a request body or headers.
