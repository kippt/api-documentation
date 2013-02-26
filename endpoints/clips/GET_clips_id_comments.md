# Clip comments - [Comment](https://github.com/kippt/api-documentation/blob/master/objects/comment.md) collection

    GET /api/clips/:clip_id/comments/

## Description

Get clip's comments. As we cap the amount of comments embedded into a clip, you might need to use this endpoint for fetching them all.

## No authentication required

No authentication is required when getting comments for a public clip but will be needed if the clip is private.

## Parameters

- _None_

## Example
**Request**

[GET /api/clips/11270125/comments/](https://grandcentral.kippt.com/api/clips/11270125/comments/)

**Return**

    {
        meta: {
            next: null,
            total_count: 1,
            previous: null,
            limit: 20,
            offset: 0
        },
        objects: [
            {
            body: "@kennethreitz you saw this?",
            created: 1361823985,
            id: 8099,
            resource_uri: "/api/clips/11270125/comments/8099/",
            user: {
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
                    follows: 1063,
                    followed_by: 20792
                },
                is_pro: true,
                resource_uri: "/api/users/1/"
                }
            }
        ]
    }
