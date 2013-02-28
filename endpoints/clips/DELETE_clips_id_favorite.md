# Unfavorite a clip

    DELETE /api/clips/:clip_id/favorite/

## Description

Unfavorites a clip for current user.

## Authentication required

Authentication required.

## Parameters

- _None_

## Errors

- <code>404</code> - Clip not found

## Example
**Request**

    DELETE /api/clips/11346574/favorite/

**Return**

    {
        is_favorite: false
    }