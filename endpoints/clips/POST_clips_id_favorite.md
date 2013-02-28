# Favorite a clip

    POST /api/clips/:clip_id/favorite/

## Description

Favorites a clip for current user.

## Authentication required

Authentication required.

## Parameters

- _None_

## Errors

- <code>404</code> - Clip not found

## Example
**Request**

    POST /api/clips/11346574/favorite/

**Return**

    {
        is_favorite: true
    }