# User's favorites - [Clip](https://github.com/kippt/api-documentation/blob/master/objects/clip.md) collection

    GET /api/clips/favorites/

## Description

Favorite clips of currently logged in user.

## Authentication required

As this endpoint return favorite clips for currently logged in user, authentication is required

## Parameters

Both <code>list</code> and <code>via</code> data for clips can be embedded into response.

- <code>include_data</code>
    - <code>list</code>
    - <code>via</code>

E.g.

    GET /api/clips/favorite/?include_data=list,via

## Example
**Request**

[GET /api/clips/favorites/](https://grandcentral.kippt.com/api/clips/favorites/)

**Return**

    {
        {
            next: "/api/clips/favorites/?limit=20&offset=20",
            previous: null,
            total_count: 124,
            limit: 20,
            offset: 0
        },
        objects: [
            {
                url_domain: "24.media.tumblr.com",
                app_url: "/katjazorina/gifs/clips/11290086",
                updated: 1361865498,
                via: null,
                likes: {
                    count: 1,
                    data: [
                        {
                        username: "jorilallo",
                        bio: "Co-founder of Kippt. I love building products.",
                        app_url: "/jorilallo",
                        twitter: "jorilallo",
                        counts: {
                            follows: 1058,
                            followed_by: 20725
                        },
                        github: "jorde",
                        avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/147d86b9-0830-49d8-a449-0421a6a4bf05/sizes/160x160",
                        is_pro: true,
                        full_name: "Jori Lallo",
                        dribbble: "jorilallo",
                        id: 1,
                        website_url: "http://about.me/jorilallo",
                        resource_uri: "/api/users/1/"
                        }
                    ]
                },
                title: "suit up",
                url: "http://24.media.tumblr.com/tumblr_ma2rxxMkfK1r5pl3ao1_r1_500.gif",
                media: {
                    images: {
                    tile: {
                        url: "https://d19weqihs4yh5u.cloudfront.net/links/99a6efe677860e73578ea670f627201c6c8d3766/350x200",
                        width: 350,
                        height: 200
                    },
                    original: {
                        url: "https://d19weqihs4yh5u.cloudfront.net/links/99a6efe677860e73578ea670f627201c6c8d3766/original",
                        width: 441,
                        height: 205
                    }
                    },
                    title: "tumblr_ma2rxxMkfK1r5pl3ao1_r1_500.gif",
                    type: "image",
                    description: null,
                    provider: {
                        url: "https://kippt.com",
                        name: "Kippt"
                    }
                },
                notes: "",
                saves: {
                    count: 0,
                    data: [ ]
                },
                list: "/api/lists/189860/",
                comments: {
                    count: 0,
                    data: [ ]
                },
                created: 1361865441,
                favicon_url: "https://www.google.com/s2/u/0/favicons?domain=24.media.tumblr.com",
                user: {
                    username: "katjazorina",
                    bio: "",
                    app_url: "/katjazorina",
                    twitter: "katjazorina",
                    counts: {
                        follows: 4,
                        followed_by: 15
                    },
                    github: "",
                    avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/41c44470-125e-41d9-ae4b-6db64dc36b53/sizes/160x160",
                    is_pro: false,
                    full_name: null,
                    dribbble: null,
                    id: 12140,
                    website_url: "",
                    resource_uri: "/api/users/12140/"
                },
                article: null,
                type: null,
                id: 11290086,
                resource_uri: "/api/clips/11290086/"
            },
            ...
        ]
    }