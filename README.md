# Kippt's API documentation

This is Kippt's API documentation. We use the API for our own web frontend and you're free to use it for your own projects and hacks.

## Mailing list and questions

If you use Kippt's API, we invite you to join [our mailing list](https://groups.google.com/forum/?fromgroups#!forum/kippt-developers). It's used for communicating changes and answering questions related to the API.

## Format

All data is returned in JSON format. Also all the data that is passed to the server, must be formatted as JSON message. To get JSONP-style responses, supply GET attribute <code>callback</code>. The <code>callback</code> parameter is the desired function name and must be alphanumeric.

## Authentication

Part of the API requires authentication and in some cases authenticated users will receive more information (e.g. _is_favorite_ status for Clip models). Easiest way to test the API is to open GET endpoint in Chrome with [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) extension installed.

Supported authentication:

- Browser session
- HTTP Basic Auth
- API Token

[Read more about authentication]()

## Versioning

Kippt's API uses timestamp based versioning which will return API version for the given date. If there's breaking changes to API, user's are given few months time to migrate.

[Read more about versioning]()

## Interacting with the API

Kippt's API uses regular <code>GET</code>, <code>POST</code>, <code>PUT</code> and <code>DELETE</code> commands.

[Making requests and error codes]()


## Pagination

When multiple objects are returned, pagination is used.

[Read more about pagination]()

## Endpoints

As this API is also used for Kippt's web app, we have had to make few design compromises and most of the resources can be queried with both numeric and alphabetical identifiers.

### Account

- [**<code>GET</code>  /api/account/**](https://github.com/kippt/api-documentation/blob/master/endpoints/account/GET_account.md)

### Users

- [**<code>GET</code>  /api/users/:user_id/**]()
- [**<code>GET</code>  /api/users/:user_id/followers/**]()
- [**<code>GET</code>  /api/users/:user_id/following/**]()
- [**<code>GET</code>  /api/users/:user_id/relationship/**]()
- [**<code>GET</code>  /api/users/self/feed/**]()
- [**<code>GET</code>  /api/users/:user_id/clips/**]()
- [**<code>GET</code>  /api/users/:user_id/likes/**]()
- [**<code>GET</code>  /api/users/:user_id/lists/**]()
- [**<code>GET</code>  /api/users/:user_id/lists/:list_id/**]()
- [**<code>GET</code>  /api/users/search/**]()
- [**<code>POST</code>  /api/users/:user_id/relationship/**]()


### Clips

- [**<code>GET</code>  /api/clips/**]()
- [**<code>GET</code>  /api/clips/favorites/**]()
- [**<code>GET</code>  /api/clips/:clip_id/**]()
- [**<code>GET</code>  /api/clips/:clip_id/comments/**]()
- [**<code>GET</code>  /api/clips/:clip_id/comments/:comment_id/**]()
- [**<code>GET</code>  /api/clips/:clip_id/likes/**]()
- [**<code>GET</code>  /api/clips/:clip_id/favorite/**]()
- [**<code>GET</code>  /api/clips/search/**]()
- [**<code>PUT</code>  /api/clips/:clip_id/**]()
- [**<code>POST</code> /api/clips/**]()
- [**<code>POST</code> /api/clips/:clip_id/comments/**]()
- [**<code>POST</code> /api/clips/:clip_id/likes/**]()
- [**<code>POST</code> /api/clips/:clip_id/favorite/**]()
- [**<code>DELETE</code> /api/clips/:clip_id/**]()
- [**<code>DELETE</code> /api/clips/:clip_id/comments/:comment_id/**]()
- [**<code>DELETE</code> /api/clips/:clip_id/likes/**]()
- [**<code>DELETE</code> /api/clips/:clip_id/favorite/**]()


### Lists

- [**<code>GET</code>  /api/lists/**]()
- [**<code>GET</code>  /api/lists/following/**]()
- [**<code>GET</code>  /api/lists/:list_id/**]()
- [**<code>GET</code> /api/lists/:list_id/clips/**]()
- [**<code>GET</code> /api/lists/:list_id/collaborators/**]()
- [**<code>GET</code>  /api/lists/:list_id/relationship/**]()
- [**<code>PUT</code>  /api/lists/:list_id/**]()
- [**<code>POST</code> /api/lists/**]()
- [**<code>POST</code> /api/lists/:list_id/collaborators**]()
- [**<code>POST</code> /api/lists/:list_id/relationship/**]()
- [**<code>DELETE</code>   /api/lists/:list_id/**]()

### Notifications

- [**<code>GET</code>  /api/notifications/**]()
- [**<code>GET</code>  /api/notifications/:notification_id/**]()
- [**<code>POST</code> /api/notifications/**]()

## Objects

- [**User**](https://github.com/kippt/api-documentation/blob/master/endpoints/objects/user.md)
- [**Clip**](https://github.com/kippt/api-documentation/blob/master/endpoints/objects/clip.md)
- [**List**](https://github.com/kippt/api-documentation/blob/master/endpoints/objects/list.md)
- [**Comment**](https://github.com/kippt/api-documentation/blob/master/endpoints/objects/comment.md)
- [**Notification**](https://github.com/kippt/api-documentation/blob/master/endpoints/objects/notification.md)

## Contribution

While designing Kippt's API, we looked how other well designed APIs are build and structured. 

- [Instagram](http://instagram.com/developer/) - Instagram's API has extremely well designed social API with following, comments and likes. Social structure in Kippt's API is heavily influenced by Instagram
- [GitHub](http://developer.github.com/) - GitHub's API is one of the few which can be navigated with textual identifiers which makes linking of the API and the web frontend possible
- [Foursquare](https://developer.foursquare.com/) - Foursquare uses timestamp based API versioning. So do we (v1 style versioning feels like boxed software).
- [500px](https://github.com/500px/api-documentation/) - This API documentation borrows heavily from 500px's structure
- [django-tastypie](http://tastypieapi.org/) - Kippt's pagination design is borrowed from Tastypie

