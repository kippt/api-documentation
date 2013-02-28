# Follow relationship to a list

    GET /api/lists/:list_id/relationship/

## Description

Get information about a relationship to a list.

## Requires authentication

This call requires authentication.

## Parameters

- _None_

## Response

Response return follow relationship as boolean.

## Errors

- <code>404</code> - List not found

## Example
**Request**

[GET /api/lists/139/relationship/](https://grandcentral.kippt.com/api/lists/139/relationship/)

**Return**

    {
        following: true
    }