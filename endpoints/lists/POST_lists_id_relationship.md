# Follow/unfollow list

    POST /api/lists/:list_id/relationship/

## Description

Change following relationship to a list.

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

Response return follow relationship as boolean. See [<code>GET /api/lists/:list_id/relationship/</code>](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_lists_id_relationship.md)

## Errors

- <code>400</code> - Invalid action (allowed values: "follow", "unfollow").
- <code>404</code> - User not found

## Example
**Request**

    POST /api/lists/139/relationship/

    {"action": "follow"}

**Return**

    {
        following: true
    }