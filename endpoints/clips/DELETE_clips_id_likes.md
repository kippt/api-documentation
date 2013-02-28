# Unlike a clip

    DELETE /api/clips/:clip_id/likes/

## Description

Unlikes a clip for current user.

## Authentication required

Authentication required.

## Parameters

- _None_

## Errors

- <code>400</code> - You haven't liked this clip.
- <code>404</code> - Clip not found

## Example
**Request**

    DELETE /api/clips/11346621/likes/

**Return**

    {}