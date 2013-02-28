# Create a list - [List](https://github.com/kippt/api-documentation/blob/master/objects/list.md) object

    POST /api/lists/

## Description

Create a list. See [List](https://github.com/kippt/api-documentation/blob/master/objects/list.md) object for fields which can be modified.

## Authentication required

Authentication required.

## Parameters

- _None_

## Example
**Request**

    POST /api/lists/

    {
        "title": "My new list",
        "description": "Where I store amazing things"
    }

**Return**

    {
        app_url: "/jorilallo/my-new-list",
        rss_url: "https://kippt.com/jorilallo/my-new-list/feed",
        updated: 1361170954,
        description: "Where I store amazing things",
        title: "My new list",
        created: 1315942545,
        collaborators: {
            count: 0,
            data: [ ]
        },
        slug: "my-new-list",
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            twitter: "jorilallo",
            counts: {
                follows: 1060,
                followed_by: 20455
            },
            github: "jorde",
            avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
            is_pro: true,
            full_name: "Jori Lallo",
            dribbble: "jorilallo",
            id: 1,
            website_url: "http://about.me/jorilallo",
            resource_uri: "/api/users/1/"
        },
        id: 15,
        is_private: true,
        resource_uri: "/api/lists/15/"
    }