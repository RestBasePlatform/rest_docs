Filters
====================================


This section describes possible filters for requesting data extraction. General view of the filter.

.. code-block:: json

    {
        "column_name": {
            "filter_type": ">"
            "value": 10
        }
        "filter_agg_type": "or"
    }


*column_name*: Name of column in table

*filter_type*: Filter type. Support value: ">" and "<"

*value*: Some value from table (now supports only numbers)

*filter_agg_type*: How combine filters.  Support values: "and" and "or"
