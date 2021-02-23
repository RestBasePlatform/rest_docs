GetData Request
====================================

.. http:get:: /GetData

   This get request returns data from table.

   **Example request**:

   .. sourcecode:: http

      GET /GetData HTTP/1.1
      Host: example.com
      Accept: application/json

      {
         "local_database_name": "some-local-name"
         "query": "SELECT * FROM public.test_table"
      }

      
   :reqheader user_token: User token. 

   :query local_database_name: Database name for query execution.
   :query query: SQL query to extract data.


   .. note::

        Schema name is neccessary in sql request, even if schema is public.

   **Example response**:

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: text/javascript

      [
        {
            "data": []
        }
      ]

   :statuscode 200: No errors.
   :statuscode 403: Access denied. Check token in a header. 
   :statuscode 400: Bad request. Check request body or headers.
   :statuscode 404: Table not found
