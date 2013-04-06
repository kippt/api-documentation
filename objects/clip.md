# <code>Clip</code>

Describes <code>Clip</code> object.

## Fields

- **<code>id</code>** (Read only) - Unique identifier
- **<code>url</code>** (Required) - Clip's URL
- **<code>url_domain</code>** (Read only) - Domain of the URL
- **<code>user</code>** (Read only) - Creator of the clip
- **<code>title</code>** - Clip's title (if not provided, automatically fetched)
- **<code>list</code>** - <code>resource_uri</code> of the List (defaults to Inbox)
- **<code>via</code>** - <code>resource_uri</code> of the original Clip if saved via feed etc
- **<code>notes</code>** - Markdown formatted notes for the Clip
- **<code>comments</code>** - (Read only) Count and array of latest comments (see below)
- **<code>likes</code>** - (Read only) Count and array of latest likes (see below)
- **<code>saves</code>** - (Read only) Count and array of latest saves (see below)
- **<code>is_favorite</code>** - (Read only) Indicates if the Clip is favorited by the current user (see below)
- **<code>media</code>** - (Read only) Media and article data for the clip (see below, currently experimental and unsupported)
- **<code>type</code>** - (Read only) Clip's type. Available values: <code>link</code>, <code>note</code> and experimental <code>image</code> and <code>file</code>
- **<code>favicon_url</code>** (Read only) - Favicon for the site
- **<code>created</code>** (Read only) - Datetime of creation
- **<code>updated</code>** (Read only) - Datetime of last update
- **<code>app_url</code>** (Read only) - Kippt's internal link
- **<code>resource_uri</code>** (Read only) - Unique resource URI for this object

## Favorite

_is_favorite_ is only included if request is authenticated.

## Media and type (**UNSUPPORTED**)

<code>media</code> describes Clip's media content and is highly dependent on the content of the saved page. One should never trust that certain information is available in <code>media</code>. Article data is <code>base64</code> encoded. Also note that <code>media</code> is only included with <code>?include_data=media</code>.

<code>media</code> is considered for Kippt's internal usage and is unsupported at the moment.

Clip also has a type which is usually <code>link</code> or <code>note</code> (see below). We're also experimenting with <code>image</code> and <code>file</code> but they behave like <code>link</code>.

## Comments, likes and saves

Clip includes total counts for comments, likes and saves. As some clips can have arbitrary number of these, only the latest ones are stored. To get all likes and comments, use their respected endpoints.

- [**<code>GET</code>  /api/clips/:clip_id/comments/**]()
- [**<code>GET</code>  /api/clips/:clip_id/likes/**]()

Saves indicates who have saved this Clip into their own lists.

# Note

If Clip is stored as a note (only <code>note</code> field is posted without <code>url</code>), <code>type</code> field has value <code>note</code>. In this case <code>url</code> is generated automatically and can't be modified afterwards.

## Parameters

- <code>include_data</code>
    - <code>via</code>
    - <code>list</code>
    - <code>media</code>

## Example

**Request**

    GET /api/clips/10654195/?include_data=media

**Return**

    {
        via: null,
        saves: {
            count: 0,
            data: [ ]
        },
        favicon_url: "https://www.google.com/s2/u/0/favicons?domain=www.romainbrasier.fr",
        is_favorite: false,
        likes: {
            count: 0,
            data: []
        },
        id: 10654195,
        app_url: "/jorilallo/awesome/clips/10654195",
        title: "404 Lemmings page",
        media: {
            title: "Développeur Web sur Lille (59), Romain Brasier.",
            description: "Développeur Web sur Lille (59), Site personnel de Romain Brasier.",
            provider: {
                url: "https://kippt.com",
                name: "Kippt"
            },
            images: {
                tile: {
                    url: "https://d19weqihs4yh5u.cloudfront.net/links/835babda8910f453807cc944f62829f3547ab928/350x200",
                    width: 350,
                    height: 200
                },
                original: {
                    url: "https://d19weqihs4yh5u.cloudfront.net/links/835babda8910f453807cc944f62829f3547ab928/original",
                    width: 50,
                    height: 33
                }
            },
            article: {
                html: "PGRpdj4KCQk8ZGl2PgoJCQkJCTxhIGhyZWY9Imh0dHA6Ly93d3cucm9tYWluYnJhc2llci5mci80MDQiPjxpbWcgc3JjPSJodHRwOi8vd3d3LnJvbWFpbmJyYXNpZXIuZnIvaW1hZ2VzL3A0MDQvZnIuanBnIj48L2E+CgkJCQkKCQk8L2Rpdj4KCQkKCQkKCQk8ZGl2PgoJCQkJCQkJPHA+CgkJCQkJVGhpcyBwYWdlIGlzIG5vIGxvbmdlciBvZiB0aGlzIHdvcmxkLjxicj4KCQkJCQlTdGF5IG9uIHRoaXMgbGFzdCByZXN1bHQgaW4gdGhlIHNhY3JpZmljZSBvZiA8Yj40MDQ8L2I+IExlbW1pbmdzLjxicj4KCQkJCQlVbmxlc3MgeW91IGRlY2lkZSB0byBzYXZlIHRoZW0gYWxsITxicj48c3Bhbj5Ib3ZlciBvdmVyIHRoZW0gdG8gYnJpbmcgYSBwYXJhY2h1dGUuPC9zcGFuPgoJCQkJPC9wPgoJCQkJCQoJCTwvZGl2PgoJCQoJCTxkaXY+CgkJCQkJCQk8cD4KCQkJCQk8YSBocmVmPSJodHRwOi8vd3d3LnJvbWFpbmJyYXNpZXIuZnIvIj5SZXR1cm4gdG8gc2l0ZTxicj48c3Bhbj4oQW5kIGxldCB0aGVtIGRpZSBwb29yIGxlbW1pbmdzKTwvc3Bhbj48L2E+CgkJCQk8L3A+CgkJCQkJCgkJPC9kaXY+CgkJCgkJCgkJCiAgICA8L2Rpdj4=",
                author_url: null,
                author: null
            },
            type: "article"
        },
        comments: {
            count: 2,
            data: [
                {
                    body: "You got to love Lemmings. And save them.",
                    user: {
                        username: "jorilallo",
                        bio: "Co-founder of Kippt. I love building products.",
                        app_url: "/jorilallo",
                        twitter: "jorilallo",
                        counts: {
                            follows: 1060,
                            followed_by: 20452
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
                    resource_uri: "/api/clips/10654195/comments/8006/",
                    id: 8006,
                    created: 1361535067
                },
                {
                    body: "All those poor Lemmings!",
                    user: {
                        username: "niklausgerber",
                        bio: "New media conceptor, problem solver & digital architect seeking to make the complex clear & beautiful.",
                        app_url: "/niklausgerber",
                        twitter: "niklausgerber",
                        counts: {
                            follows: 21,
                            followed_by: 4
                        },
                        github: "niklausgerber",
                        avatar_url: "http://kippt-image-vault.herokuapp.com/vaults/avatars/images/09ed9863-7b7b-4a6e-9cab-a2262f377993/sizes/160x160",
                        is_pro: false,
                        full_name: null,
                        dribbble: "niklausgerber",
                        id: 46793,
                        website_url: "http://niklausgerber.com/",
                        resource_uri: "/api/users/46793/"
                    },
                    resource_uri: "/api/clips/10654195/comments/6955/",
                    id: 6955,
                    created: 1359008573
                }
            ]
        },
        type: "link",
        updated: 1360890944,
        user: {
            username: "jorilallo",
            bio: "Co-founder of Kippt. I love building products.",
            app_url: "/jorilallo",
            twitter: "jorilallo",
            counts: {
                follows: 1060,
                followed_by: 20452
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
        url_domain: "www.romainbrasier.fr",
        created: 1358983868,
        url: "http://www.romainbrasier.fr/404.php?lang=en",
        notes: "Awesome 404 page",
        list: "/api/lists/13/",
        resource_uri: "/api/clips/10654195/"
    }