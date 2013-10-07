# Pagination

When requesting collections of objects, result will be paginated with following format:

    {
        "meta": {
            "limit": 20,
            "next": "/api/clips/?limit=20&offset=20",
            "offset": 0,
            "previous": null
        },
        "objects": [
                {
                    "id": 15,
                    ...
                },
            ...
        ]
    }

Pagination is limited to max. 200 items per page at the time but it's recommended to stick with the default 20. To query more items, follow <code>next</code> parameter.

**Deprecation of <code>total_count</code>:** Pagination used to include total count for items but it has since removed to improve performance.
