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

For more information about tables list reuqest visit: :doc:`rest_docs/table/index`.


=================
Add users
=================

To add the first user, use :doc:`generate_user_token`.

.. code-block:: bash

 curl --location --request PUT 'localhost:54541/GenerateUserToken?token_name=TOKEN_NAME_HERE' --header 'admin_token: ADMIN_TOKEN_HERE'

For more information about adding a user, visit the page. :doc:`rest_docs/tokens/generate_user_token`.

To grant the user rights to retrieve data from tables use: 

.. code-block:: bash

 curl --location --request POST 'localhost:54541/GrantTableAccess?local_table_name=LOCAL_TABLE_NAME_HERE&user_token=USER_TOKEN_HERE' --header 'admin_token: ADMIN_TOKEN_HERE'

For more information about adding an access, visit the page. :doc:`rest_docs/tokens/grant_table_access`.


=================
Data extraction
=================

To extract data use

.. code-block:: bash

 curl --location --request GET 'http://127.0.0.1:54541/GetData?query=QUERY_HERE&local_database_name=LOCAL_DATABASE_NAME_HERE' \
    --header 'user_token: USER_TOKEN_HERE'

For more information about data extraction, visit the page :doc:`rest_docs/get_data_request`.