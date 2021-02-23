Rest API documentation
====================================

.. toctree::

   database/index
   table/index

   get_admin_token
   generate_user_token
   grant_table_access
   get_data_request


This section describes the basic commands for communicating with the server via Rest requests

To get started, you need to download the docker image from the docker hub and run it.

.. sourcecode:: bash
   
   docker run -p 54541:54541 restbase/restbase-server 

First steps
----------

After starting the docker, you need to generate an administrator token using :doc:`../rest_docs/get_admin_token`.

After starting the container and getting the administrator token, you need to add the database using :doc:`database/add_database`.

To make sure that the database is added, use :doc:`database/list_database`.

After adding the database, you can check the list of all read tables using :doc:`tables/index`.


Add users
----------

To add the first user, use :doc:`generate_user_token`.

To grant the user rights to retrieve data from tables, use :doc:`grant_table_access`.



Data extraction
----------

To extract data use :doc:`get_data_request`.