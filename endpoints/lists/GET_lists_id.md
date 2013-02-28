# List - [List](https://github.com/kippt/api-documentation/blob/master/objects/list.md) object

    GET /api/lists/:list_id/

## Description

Get a list

## No authentication required

No authentication is required when getting a public list but will be needed if the list is private.

## Parameters

- _None_

## Example
**Request**

[GET /api/lists/13/](https://grandcentral.kippt.com/api/lists/13/)

**Return**

    {
        app_url: "/jorilallo/awesome",
        rss_url: "https://kippt.com/jorilallo/awesome/feed",
        updated: 1361888610,
        description: "My collection of random awesome links I find on the Interwebs",
        title: "Awesome",
        created: 1315942545,
        collaborators: {
            count: 0,
            data: [ ]
        },
        slug: "awesome",
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            twitter: "jorilallo",
            counts: {
                follows: 1064,
                followed_by: 21006
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
        id: 13,
        is_private: false,
        resource_uri: "/api/lists/13/"
    }