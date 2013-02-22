# <code>User</code>

Describes <code>User</code> object. Also used when listing people who have liked a Clip.

## Parameters

None

## Example

**Request**

    GET /api/users/self/

**Return**

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
            follows: 1060,
            followed_by: 20452
        },
        is_pro: true,
        resource_uri: "/api/users/1/"
    }