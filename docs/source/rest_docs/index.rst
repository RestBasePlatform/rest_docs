Rest API documentation
====================================



This section describes the basic commands for communicating with the server via Rest requests

To get started, you need to download the docker image from the docker hub and run it.

.. sourcecode:: bash
   
   docker run -p 54541:54541 restbase/restbase-server 


Follow :doc:`../quickstart` for more detailed information.

.. toctree::

   database/index
   table/index
   tokens/index

   get_admin_token
   generate_user_token
   grant_table_access
   get_data_request
   logs