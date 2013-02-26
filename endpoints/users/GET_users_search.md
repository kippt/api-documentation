# User search - [User](https://github.com/kippt/api-documentation/blob/master/objects/user.md) collection

    GET /api/users/search/

## Description

Search users with keywords. Index is build out of username, description and social profiles.

**IMPORTANT NOTE:** This is currently being tested and should be considered as unsupported endpoint.

## Authentication required

Authentication is required for this endpoint.

## Parameters

- <code>q</code> - Search parameter

## Errors

- <code>400</code> - Missing search parameter

## Example
**Request**

[GET /api/users/search/?q=jorilallo](https://grandcentral.kippt.com/api/users/search/?q=jorilallo)

**Return**

    meta: {
        total_count: 1,
        next: null,
        limit: 20,
        offset: 0,
        query: "jorilallo",
        previous: null
    },
    objects: [
        {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
            twitter: "jorilallo",
            id: 1,
            github: "jorde",
            website_url: "http://about.me/jorilallo",
            full_name: "Jori Lallo",
            dribbble: "jorilallo",
            counts: {
                follows: 1061,
                followed_by: 20371
            },
            is_pro: true,
            resource_uri: "/api/users/1/"
        }
    ]