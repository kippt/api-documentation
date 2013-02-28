# Get latest notifications - [Notification](https://github.com/kippt/api-documentation/blob/master/objects/notification.md) collection **UNSUPPORTED**

    GET /api/notifications/

## Description

Get latest notifications.

## Authentication required

As this endpoint return notifications for currently logged in user, authentication is required

## Parameters

- <code>include_data</code>
    - <code>clip</code>
    - <code>list</code>
- <code>since</code> - Updated after specific timestamp

## Example
**Request**

[GET /api/notifications/](https://grandcentral.kippt.com/api/notifications/)

**Return**

    {
        {
            next: "/api/notifications/?limit=20&offset=20",
            total_count: 1307,
            previous: null,
            limit: 20,
            offset: 0
        },
        objects: [
            {
                item_url: "/jkan",
                created: 1361414461,
                is_seen: true,
                user: {
                    username: "jkan",
                    bio: null,
                    app_url: "/jkan",
                    avatar_url: "https://d17f28g3dsa4vh.cloudfront.net/img/default-avatar.png",
                    twitter: null,
                    id: 50846,
                    github: null,
                    website_url: null,
                    full_name: null,
                    dribbble: null,
                    counts: {
                        follows: 83,
                        followed_by: 4
                    },
                    is_pro: false,
                    resource_uri: "/api/users/50846/"
                },
                type: "follow",
                id: 82889,
                resource_uri: "/api/notifications/82889/"
            },
            ...
        ]
    }