# Delete a comment

    DELETE /api/clips/:clip_id/comments/:comment_id/

## Description

Deletes a comment. Comment can be deleted by its creator and clip's creator.

## Authentication required

Authentication required.

## Parameters

- _None_

## Errors

- <code>400</code> - Only clip and comment owners can delete clip's comments
- <code>404</code> - Clip or comment not found

## Example
**Request**

    DELETE /api/clips/11074345/

**Return**

_None_