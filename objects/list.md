# <code>List</code>

Describes <code>List</code> object.

## Fields

- **<code>id</code>** (Read only) - Unique identifier
- **<code>title</code>** - List's title
- **<code>slug</code>** - (Read only) Slug for urls
- **<code>is_private</code>** - Privacy (default: <code>true</code>)
- **<code>user</code>** (Read only) - Creator of the clip
- **<code>description</code>** - Description
- **<code>collaborators</code>** - (Read only) Count and array of collaborators (see below)
- **<code>created</code>** (Read only) - Datetime of creation
- **<code>updated</code>** (Read only) - Datetime of last update
- **<code>app_url</code>** (Read only) - Kippt's internal link
- **<code>rss_url</code>** (Read only) - RSS feed
- **<code>resource_uri</code>** (Read only) - Unique resource URI for this object

## Parameters

None

## Collaborators (**UNSUPPORTED**)

List includes total counts for collaborators. As some lists can have arbitrary number of these, only the latest ones are stored. To get all collaborators, use their respected endpoints.

- [**<code>GET</code>  /api/lists/:list_id/collaborators/**]()

## Example

**Request**

    GET /api/lists/13/

**Return**

    {
        app_url: "/jorilallo/awesome",
        rss_url: "https://kippt.com/jorilallo/awesome/feed",
        updated: 1361170954,
        description: "My collection of random awesome links I find on the Interwebs",
        title: "Awesome",
        created: 1315942545,
        collaborators: {
            count: 0,
            data: [ ]
        },
        slug: "awesome",
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            twitter: "jorilallo",
            counts: {
                follows: 1060,
                followed_by: 20455
            },
            github: "jorde",
            avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
            is_pro: true,
            full_name: "Jori Lallo",
            dribbble: "jorilallo",
            id: 1,
            website_url: "http://about.me/jorilallo",
            resource_uri: "/api/users/1/"
        },
        id: 13,
        is_private: false,
        resource_uri: "/api/lists/13/"
    }
