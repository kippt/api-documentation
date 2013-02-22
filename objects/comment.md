# <code>Comment</code>

Describes <code>Comment</code> object.

## Parameters

None

## Example

**Request**

    GET /api/clips/10654195/comments/8006/

**Return**

    {
        id: 8006,
        body: "You got to love Lemmings. And save them.",
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
                follows: 1060,
                followed_by: 20452
            },
            is_pro: true,
            resource_uri: "/api/users/1/"
        },
        created: 1361535067,
        resource_uri: "/api/clips/10654195/comments/8006/"
    }