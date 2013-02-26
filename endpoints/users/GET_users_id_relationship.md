# Follow relationship to another user

    GET /api/users/:user_id/relationship/

## Description

Get information about a relationship to another user. <code>user_id</code> follows the same pattern as [<code>GET /api/users/:user_id/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id.md) except <code>self</code> isn't allowed (user can't follow themselves)

## Requires authentication

This call requires authentication.

## Parameters

- _None_

## Response

Response return follow relationship as boolean.

## Errors

- <code>400</code> - User can't follow him/herself
- <code>404</code> - User not found

## Example
**Request**

[GET /api/users/3/relationship/](https://grandcentral.kippt.com/api/users/3/relationship)

**Return**

    {
        following: true
    }