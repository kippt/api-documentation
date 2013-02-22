# <code>Notification</code> **UNSUPPORTED**

Describes <code>Notification</code> object. This is meant for Kippt's internal usage and is unsupported. We're not kidding when we say this.

## Notification types

Notifications can have several sources. App should always whitelist supported ones. At the moment every type includes as combination of parameters <code>user</code>, <code>clip</code>, <code>list</code>, <code>comment</code> and <code>like</code>.

- <code>clip</code> New clip in list
    - <code>clip</code> Clip that got saved
- <code>clip_mention</code> Clip mention
    - <code>clip</code> Clip which includes the mention
- <code>clip_comment</code> New comment
    - <code>clip</code> Clip which includes the new comment
    - <code>comment</code> Comment data
- <code>clip_comment_mention</code> Comment mention
    - <code>clip</code> Clip which includes the new comment with mention
    - <code>comment</code> Comment with mention
- <code>clip_like</code> Clip like
    - <code>clip</code> Clip which includes the new like
    - <code>like</code> Like data
- <code>clip_save</code> Clip save
    - <code>clip</code> Clip which got saved
    - <code>user</code> Who saved the clip
- <code>follow</code> New follower
    - <code>user</code> Who followed you

## Example

**Request**

    GET /api/notifications/82889/

**Return**

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
