# [User](https://github.com/kippt/api-documentation/blob/master/objects/user.md) resource

    GET /api/users/:user_id/

## Description

Get public user data based on user's ID, username or for currently logged in user.

- <code>/api/users/1/</code> - Get User with ID
- <code>/api/users/jorilallo/</code> - Get User with username (usually mapped from URL)
- <code>/api/users/self/</code> - Get logged in user

## No authentication required

No authentication is required but logged in user can request his/hers data (similar to <code>/api/account/</code>).

## Parameters

- _None_

## Errors

- <code>404</code> - User not found

## Example
**Request**

    [GET /api/users/1/](https://grandcentral.kippt.com/api/users/1/)

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
            follows: 1061,
            followed_by: 20371
        },
        is_pro: true,
        resource_uri: "/api/users/1/"
    }