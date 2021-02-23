Quickstart
============




=================
First steps
=================

After starting the docker, you need to generate an administrator token using :doc:`../rest_docs/get_admin_token`.

After starting the container and getting the administrator token, you need to add the database using :doc:`database/add_database`.

To make sure that the database is added, use :doc:`database/list_database`.

After adding the database, you can check the list of all read tables using :doc:`tables/index`.


=================
Add users
=================

To add the first user, use :doc:`generate_user_token`.

To grant the user rights to retrieve data from tables, use :doc:`grant_table_access`.


=================
Data extraction
=================

To extract data use :doc:`get_data_request`.