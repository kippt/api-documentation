# Like a clip

    POST /api/clips/:clip_id/likes/

## Description

Likes a clip for current user.

## Authentication required

Authentication required.

## Parameters

- _None_

## Errors

- <code>400</code> - Can't like own clip.
- <code>404</code> - Clip not found

## Example
**Request**

    POST /api/clips/11346621/likes/

**Return**

    {}