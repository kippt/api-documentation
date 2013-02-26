# Clip likes - [User](https://github.com/kippt/api-documentation/blob/master/objects/user.md) collection

    GET /api/clips/:clip_id/likes/

## Description

Get clip's likes. As we cap the amount of likes embedded into a clip, you might need to use this endpoint for fetching them all.

## No authentication required

No authentication is required when getting likes for a public clip but will be needed if the clip is private.

## Parameters

- _None_

## Example
**Request**

[GET /api/clips/11270125/likes/](https://grandcentral.kippt.com/api/clips/11270125/likes/)

**Return**

    {
        meta: {
            next: null,
            total_count: 2,
            previous: null,
            limit: 20,
            offset: 0
        },
        objects: [
            {
                username: "alextrob",
                bio: "Alex Robinson, Developer of Clippt - a Kippt client for iOS.",
                app_url: "/alextrob",
                avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/7184d66f-af3a-4066-85f1-d781bf57a2ef/sizes/160x160",
                twitter: "alextrob",
                id: 11909,
                github: "alextrob",
                website_url: "http://alextrob.net/",
                full_name: "",
                dribbble: "",
                counts: {
                    follows: 21,
                    followed_by: 16
                },
                is_pro: true,
                resource_uri: "/api/users/11909/"
            },
            {
                username: "nc21",
                bio: "Devourer of books, science, tech, space and art. In search of that elusive meaningful conversation that lasts hours. Over a large mug of coffee....",
                app_url: "/nc21",
                avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/4077a0ee-3240-422f-b857-0f6b8f4db39f/sizes/160x160",
                twitter: "TheFictonaut",
                id: 42590,
                github: "",
                website_url: "N. Chanis",
                full_name: "",
                dribbble: "",
                counts: {
                    follows: 2,
                    followed_by: 1
                },
                is_pro: false,
                resource_uri: "/api/users/42590/"
            }
        ]
    }
