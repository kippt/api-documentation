# Interacting with the API

## Making requests

### Getting resources (GET)

When requesting multiple objects, the request will be paginated:

_Example:_ <code>curl --user name:password https://kippt.com/api/lists/</code>

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

You can control the range by settings <code>limit</code> and <code>offset</code> parameters on call:

_Example:_ <code>curl --user name:password https://kippt.com/api/lists/?limit=25&offset=50</code>

In some cases it's easier to get referenced objects with embedded data instead of resource URIs (e.g. for search results you would also like to know lists). You can do this with <code>include_data</code> parameter and with comma separated list of resources you want to embed (_user_ is always embedded):

_Example:_ <code>curl --user name:password https://kippt.com/api/clips/1/?include_data=list</code>

    {
        "id": "1",
        "url": "https://kippt.com",
        "list": {
            "id": 12,
            "resource_uri": "/api/lists/12/",
            ...
        },
        ...
    }

To get single object, just call it by its ID:

_Example:_ <code>curl --user name:password https://kippt.com/api/lists/1/</code>

    {
        "id": "1",
        "slug": "inbox",
        "title": "Inbox",
        ...
    }

### Creating a resource (POST)

Use POST to create new objects. You need to supply the _Required__ attributes for a successful request. When supplying a reference to another object, use its <code>id</code> or <code>resource_uri</code> to identify the object.

_Example:_ <code>curl --user name:password -X POST --data '{"url": "https://kippt.com", "list": "/api/lists/12/"}' https://kippt.com/api/clips/</code>

Successful response comes back with <code>201 CREATED</code> code and object's JSON.

### Updating an existing resource (PUT)

PUT lets you update existing resources. You need to use resource's URI and supply changed information:

_Example:_ <code>curl --user name:password -X PUT --data '{"title": "New list name"}' https://kippt.com/api/lists/5/</code>

Successful response comes back with <code>200 OK</code> code and object's JSON.

### Delete a resource (DELETE)

You can delete a resource by calling a DELETE with resources URI:

_Example:_ <code>curl --user name:password -X DELETE  https://kippt.com/api/lists/5/</code>

Successful response comes back with <code>204 NO CONTENT</code> code but don't be naughty: we won't delete system created Inbox.

## Error codes

- <code>200 OK</code> It's all good bro, you hit the right endpoint with right credentials
- <code>201 Created</code> New object saved
- <code>302 Found</code> Wrong url, follow <code>Location</code>
- <code>400 Bad Request</code> Returns JSON with the error message
- <code>401 Unauthorized</code> Couldn't authenticate your request
- <code>404 Not Found</code> No such object
- <code>405 Method Not Allowed</code> Supplied HTTP method not allowed for this endpoint
- <code>500 Internal Server Error</code> Something went wrong
- <code>503 Service Unavailable</code> Your connection is being throttled or the service is down for maintenance

All error messages (response code 400 and up) in the responses follow the following pattern:

    {
        "message": "Not found."
    }