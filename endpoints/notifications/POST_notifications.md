# Mark notifications as read **UNSUPPORTED**

    POST /api/notifications/

## Description

Mark notifications as read.

## Authentication required

Authentication is required

## Errors:

- <code>400</code> - Invalid action (allowed values: "mark_seen").

## Example
**Request**

    POST /api/notifications/

    {
        "action": "mark_seen"
    }

**Return**

    {}