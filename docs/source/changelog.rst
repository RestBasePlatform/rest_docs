*********
Changelog
*********

v0.1.1
======

:Date: March, 2021

Fixes
-----

* Fix access from any token to rename table in 'PostTable' request

New Features
------------

* Added MySQL suppot (`#31 <https://github.com/RestBaseApi/restbase/commit/21ec6007511d6395d1beefc05556157b45565bb7>`_)
* Added logging (`#37 <https://github.com/RestBaseApi/restbase/pull/37>`_)
* Added rest access to logs :doc:`rest_docs/logs`

Code changes
-------------
* Add healthcheck condiction for databases in tests



v0.1.2
======

:Date: April, 2021

Fixes
-----

* Fixed 500 error when re-requesting to create a token

v0.1.3
======

:Date: April, 2021

Fixes
-----

* Fixed 500 error when one database transaction failed. (`#46 <https://github.com/RestBaseApi/restbase/pull/46>`_)
