# Pagination

When requesting collections of objects, result will be paginated with following format:

    {
        "meta": {
            "limit": 20,
            "next": "/api/clips/?limit=20&offset=20",
            "offset": 0,
            "previous": null,
            "total_count": 33
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

It's worth noting that Feed endpoint (<code>/api/users/self/feed/</code>) lacks <code>total_count</code> parameter and one should stop paginating when <code>next</code> is <code>null</code>.

[Making requests and error codes]()