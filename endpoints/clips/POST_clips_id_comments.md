# Create a clip comment - [Comment](https://github.com/kippt/api-documentation/blob/master/objects/comment.md) object

    POST /api/clips/:clip_id/comments/

## Description

Create a new comment for clip. See [Comment](https://github.com/kippt/api-documentation/blob/master/objects/comment.md) object for fields which can be modified.

## Authentication required

Authentication required.

## Parameters

- _None_

## Example
**Request**

    POST /api/clips/11346076/comments/

    {
        "body": "It's fantastic to see how stuff got made back in the day."
    }

**Return**

    {
        body: "It's fantastic to see how stuff got made back in the day.",
        created: 1362062283,
        id: 8244,
        resource_uri: "/api/clips/11346076/comments/8244/",
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
                follows: 1064,
                followed_by: 21000
            },
            is_pro: true,
            resource_uri: "/api/users/1/"
        }
    }