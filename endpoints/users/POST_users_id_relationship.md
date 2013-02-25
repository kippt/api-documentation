# Follow/unfollow user

    POST /api/users/:user_id/relationship/

## Description

Change following relationship to another user. <code>user_id</code> follows the same pattern as [<code>GET /api/users/:user_id/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id.md) except <code>self</code> isn't allowed (user can't follow themselves)

## Requires authentication

This call requires authentication.

## Parameters

- _None_

## Request

Request must contain valid JSON data with following values:

- <code>action</code>
    - <code>follow</code>
    - <code>unfollow</code>

E.g.

    {"action": "follow"}

## Response

Response return follow relationship as boolean. See [<code>GET /api/users/:user_id/relationship/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_relationship.md)

## Errors

- <code>400</code> - User can't follow him/herself
- <code>404</code> - User not found

## Example
**Request**

[POST /api/users/3/relationship/](https://grandcentral.kippt.com/api/users/3/relationship)

    {"action": "follow"}

**Return**

    {
        following: true
    }