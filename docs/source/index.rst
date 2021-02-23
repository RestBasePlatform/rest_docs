Welcome to RestBase's documentation!
====================================

RestBase provides the ability to collect all databases in one place, providing a convenient way to differentiate access to data within databases and quickly add new users. 
All communication with the server takes place via REST requests. Access differentiation is based on the paradigm of unique access keys (tokens).

To get started, you need to download the docker image from the docker hub and run it.

.. sourcecode:: bash
   
   docker run -p 54541:54541 restbase/restbase-server 

After starting the docker, you need to generate an administrator token using :doc:`rest_docs/get_admin_token`.
Description of the next steps in :doc:`quickstart`.

.. toctree::

  quickstart
  rest_docs/index
  