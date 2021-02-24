Quickstart
============


=================
First steps
=================

After starting the docker, you need to generate an administrator token using.

.. code-block:: bash

    curl --location --request GET 'localhost:54541/GenerateAdminToken'

For more information about admin token: :doc:`rest_docs/tokens/get_admin_token`.

After starting the container and getting the administrator token, you need to add the database using 

.. code-block:: bash

    curl --location --request PUT 'http://localhost:54541/Database?base_type=postgres&description=some-base&local_database_name=some_local_name&ip=SOME_IP&port=SOME_PORT&username=SOME_USER&password=SOME_PASSWORD&database=SOME_DATABASE' \
    --header 'admin_token: ADMIN_TOKEN_HERE' 

For more information about database adding visit:  :doc:`rest_docs/database/add_database`

To make sure that the database is added, use

.. code-block:: bash

    curl --location --request GET 'http://localhost:54541/Database/list' \
    --header 'admin_token: ADMIN_TOKEN_HERE'

For more information about database list reuqest visit: :doc:`rest_docs/database/list_database`.

After adding the database, you can check the list of all read tables use

.. code-block:: bash

    curl --location --request GET 'http://localhost:54541/Table/list' \
    --header 'admin_token: ADMIN_TOKEN_HERE'

For more information about tables list reuqest visit: :doc:`rest_docs/tables/index`.


=================
Add users
=================

To add the first user, use :doc:`generate_user_token`.

To grant the user rights to retrieve data from tables, use :doc:`grant_table_access`.


=================
Data extraction
=================

To extract data use :doc:`get_data_request`.