# User's list - [List](https://github.com/kippt/api-documentation/blob/master/objects/list.md) object

    GET /api/users/:user_id/lists/:list_id/

## Description

This endpoint return user's list. This endpoint is somewhat redundant with <code>/api/lists/:list_id/</code> if used with numeric <code>list_id</code>. The reason for the existence of this endpoint is that it can be mapped to URLs. This is important for Kippt's web client for most likely useless for everyone else. 

<code>user_id</code> follows the same pattern as [GET <code>/api/users/:user_id/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id.md)

<code>list_id</code> supports both numeric IDs and alphabetical slugs:

- <code>/api/users/1/lists/5/</code> - Get a list with ID
- <code>/api/users/jorilallo/lists/awesome/</code> - Get a list with username and slug

## No authentication required

No authentication is required.

## Errors

- <code>404</code> - User or list not found

## Example
**Request**

[GET /api/users/1/lists/286222/](https://grandcentral.kippt.com/api/users/1/lists/286222/)

**Return**

    {
        rss_url: "https://kippt.com/jorilallo/watches/feed",
        updated: 1360932117,
        description: "I'm a watch nerd",
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            twitter: "jorilallo",
            counts: {
                follows: 1061,
                followed_by: 20782
            },
            full_name: "Jori Lallo",
            dribbble: "jorilallo",
            id: 1,
            app_url: "/jorilallo",
            github: "jorde",
            avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
            is_pro: true,
            website_url: "http://about.me/jorilallo",
            resource_uri: "/api/users/1/"
        },
        id: 286222,
        is_private: false,
        app_url: "/jorilallo/watches",
        collaborators: {
            count: 0,
            data: [ ]
        },
        title: "Watches",
        created: 1360932117,
        slug: "watches",
        resource_uri: "/api/lists/286222/"
    }