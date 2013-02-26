# Create a clip - [Clip](https://github.com/kippt/api-documentation/blob/master/objects/clip.md) object

    POST /api/clips/

## Description

Create a clip. See [Clip](https://github.com/kippt/api-documentation/blob/master/objects/clip.md) object for fields which can be modified.

## Authentication required

Authentication required.

## Parameters

- _None_

## Example
**Request**

    POST /api/clips/

    {
        "url": "http://blog.kippt.com/2013/01/11/keyboard-shortcut/",
        "notes": "Remember to set keyboard shortcuts for Chrome"
    }

**Return**

    {
        via: null,
        saves: {
            count: 0,
            data: [ ]
        },
        favicon_url: "https://www.google.com/s2/u/0/favicons?domain=blog.kippt.com",
        is_favorite: false,
        likes: {
            count: 0,
            data: [ ]
        },
        id: 11298740,
        app_url: "/jorilallo/inbox/clips/11298740",
        title: "Add keyboard shortcut to the Kippt Chrome Extension - Kippt Blog",
        media: null,
        type: "link",
        updated: 1361912161,
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
            twitter: "jorilallo",
            id: 1,
            github: "jorde",
            website_url: "http://about.me/jorilallo",
            full_name: "Jori Lallo",
            dribbble: "jorilallo",
            counts: {
                follows: 1063,
                followed_by: 20796
            },
            is_pro: true,
            resource_uri: "/api/users/1/"
        },
        url_domain: "blog.kippt.com",
        created: 1361912159,
        url: "http://blog.kippt.com/2013/01/11/keyboard-shortcut/",
        notes: "Remember to set keyboard shortcuts for Chrome",
        list: "/api/lists/1/",
        resource_uri: "/api/clips/11298740/"
    }