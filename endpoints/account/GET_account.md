# User Resources

    GET /api/account/

## Description

Get logged in user's user profile and optionally API token for [API token auth]

## Requires authentication

This request requires authentication always.

## Parameters

You can include 

- __include_data__
    - _api_token_

## Return format

JSON representation of User object for currently logged in user.

## Errors

- __401__ - Not authenticated

## Example
**Request**

    [GET /api/account/?include_data=api_token](https://grandcentral.kippt.com/api/account/?include_data=api_token)

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
        api_token: "123344465665756876867845523",
        dribbble: "jorilallo",
        counts: {
            follows: 1061,
            followed_by: 20371
        },
        is_pro: true,
        resource_uri: "/api/users/1/"
    }

