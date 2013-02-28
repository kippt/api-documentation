# User's lists - [List](https://github.com/kippt/api-documentation/blob/master/objects/list.md) collection

    GET /api/lists/

## Description

Get user's lists, both public and private.

## Authentication required

As this endpoint return lists for currently logged in user, authentication is required

## Parameters

_None_

## Example
**Request**

[GET /api/lists/](https://grandcentral.kippt.com/api/lists/)

**Return**

    {
        meta: {
            next: "/api/lists/?limit=20&offset=20",
            total_count: 34,
            previous: null,
            limit: 20,
            offset: 0
        },
        objects: [
            {
                rss_url: "https://kippt.com/jorilallo/inbox/feed/asd4e82d91e65c35asdsda",
                updated: 1357643161,
                description: "",
                user: {
                    username: "jorilallo",
                    bio: "Co-founder of Kippt. I love building products.",
                    twitter: "jorilallo",
                    counts: {
                        follows: 1064,
                        followed_by: 21006
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
                id: 1,
                is_private: true,
                app_url: "/inbox",
                collaborators: {
                    count: 0,
                    data: [ ]
                },
                title: "Inbox",
                created: 1315880146,
                slug: "inbox",
                resource_uri: "/api/lists/1/"
            },
            ...
        ]
    }