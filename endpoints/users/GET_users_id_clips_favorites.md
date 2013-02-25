# User's favorites - [Clip](https://github.com/kippt/api-documentation/blob/master/objects/clip.md) collection

    GET /api/users/:user_id/clips/favorites/

## Description

User's public favorites (can be hidden, then <code>count: 0</code> is returned). <code>user_id</code> follows the same pattern as [GET <code>/api/users/:user_id/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id.md)

## No authentication required

No authentication is required.

## Parameters

- _None_

## Errors

- <code>404</code> - User not found

## Example
**Request**

[GET /api/users/1/clips/favorites/](https://grandcentral.kippt.com/api/users/1/clips/favorites/)

**Return**

    {
        meta: {
            next: "/api/users/1/followers/?limit=20&offset=20",
            total_count: 15060,
            previous: null,
            limit: 20,
            offset: 0
        },
        objects: [
            {
                username: "karrisaarinen",
                bio: "Co-founder and designer of Kippt (YC S12). Co-founded Rails Girls and ArcticStartup.",
                twitter: "karrisaarinen",
                counts: {
                    follows: 1248,
                    followed_by: 20661
                },
                full_name: "Karri Saarinen",
                dribbble: "karrisaarinen",
                id: 3,
                app_url: "/karrisaarinen",
                github: "ksaa",
                avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/2ddb18c3-8b0b-4bab-a901-daebed6e7097/sizes/160x160",
                is_pro: true,
                website_url: "http://karrisaarinen.com/",
                resource_uri: "/api/users/3/"
            },
            ...
        ]
    }