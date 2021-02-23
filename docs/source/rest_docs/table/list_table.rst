ListTable Request
====================================

.. http:get:: /Database/list

   This get request returns a list of tables that the token has access to.

   **Example request**:

    .. sourcecode:: http

      GET /Database/List HTTP/1.1
      Host: example.com
      Accept: application/json
    
   :reqheader user_token: User token. 
   :reqheader admin_token: Admin token. 



   .. note::
   
        Only one token should be provided. If provided both user token will be ignored.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      {
        "List": [
            "table-local-name-1",
            "table-local-name-2",
            "table-local-name-3",
            "table-local-name-4"
        ],
        "status": "success"
    }

   :statuscode 200: No errors.
   :statuscode 400: Bad request. Check request body.
