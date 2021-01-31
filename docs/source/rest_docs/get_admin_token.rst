GetAdminToken Request
====================================


.. http:get:: /GetAdminToken/

   This get request generates an admin token for restbase-server.  

   **Example request**:

   .. sourcecode:: http

      GET /GetAdminToken HTTP/1.1
      Host: example.com
      Accept: application/json

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: text/javascript

      [
        {
            "admin-token": "some-admin-token"
        }
      ]

   :statuscode 200: No errors.
   :statuscode 409: Token already exists. 


   .. note::

        You can only get it once. Save it in a safe place.