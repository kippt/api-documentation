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

[Read more about versioning](https://github.com/kippt/api-documentation/blob/master/basics/versioning.md)

## Interacting with the API

Kippt's API uses regular <code>GET</code>, <code>POST</code>, <code>PUT</code> and <code>DELETE</code> commands.

[Making requests and error codes](https://github.com/kippt/api-documentation/blob/master/basics/making_requests_and_error_codes.md)

## Pagination

When multiple objects are returned, pagination is used.

[Read more about pagination](https://github.com/kippt/api-documentation/blob/master/basics/pagination.md)

## Endpoints

As this API is also used for Kippt's web app, we have had to make few design compromises and most of the resources can be queried with both numeric and alphabetical identifiers.

### Account

- [**<code>GET</code>  /api/account/**](https://github.com/kippt/api-documentation/blob/master/endpoints/account/GET_account.md)

### Users

- [**<code>GET</code>  /api/users/:user_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id.md)
- [**<code>GET</code>  /api/users/:user_id/followers/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_followers.md)
- [**<code>GET</code>  /api/users/:user_id/following/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_following.md)
- [**<code>GET</code>  /api/users/:user_id/relationship/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_relationship.md)
- [**<code>GET</code>  /api/users/self/feed/**]()
- [**<code>GET</code>  /api/users/:user_id/clips/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_clips.md)
- [**<code>GET</code>  /api/users/:user_id/clips/likes/**]()
- [**<code>GET</code>  /api/users/:user_id/lists/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_lists.md)
- [**<code>GET</code>  /api/users/:user_id/lists/:list_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_id_lists_id.md)
- [**<code>GET</code>  /api/users/search/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/GET_users_search.md)
- [**<code>POST</code>  /api/users/:user_id/relationship/**](https://github.com/kippt/api-documentation/blob/master/endpoints/users/POST_users_id_relationship.md)


### Clips

- [**<code>GET</code>  /api/clips/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips.md)
- [**<code>GET</code>  /api/clips/favorites/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_favorites.md)
- [**<code>GET</code>  /api/clips/:clip_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_id.md)
- [**<code>GET</code>  /api/clips/:clip_id/comments/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_id_comments.md)
- [**<code>GET</code>  /api/clips/:clip_id/comments/:comment_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_id_comments_id.md)
- [**<code>GET</code>  /api/clips/:clip_id/favorite/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_id_favorite.md)
- [**<code>GET</code>  /api/clips/:clip_id/likes/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_id_likes.md)
- [**<code>GET</code>  /api/clips/search/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/GET_clips_search.md)
- [**<code>PUT</code>  /api/clips/:clip_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/PUT_clips_id.md)
- [**<code>POST</code> /api/clips/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/POST_clips.md)
- [**<code>POST</code> /api/clips/:clip_id/comments/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/POST_clips_id_comments.md)
- [**<code>POST</code> /api/clips/:clip_id/likes/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/POST_clips_id_likes.md)
- [**<code>POST</code> /api/clips/:clip_id/favorite/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/POST_clips_id_favorite.md)
- [**<code>DELETE</code> /api/clips/:clip_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/DELETE_clips_id.md)
- [**<code>DELETE</code> /api/clips/:clip_id/comments/:comment_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/DELETE_clips_id_comments_id.md)
- [**<code>DELETE</code> /api/clips/:clip_id/favorite/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/DELETE_clips_id_favorite.md)
- [**<code>DELETE</code> /api/clips/:clip_id/likes/**](https://github.com/kippt/api-documentation/blob/master/endpoints/clips/DELETE_clips_id_likes.md)


### Lists

- [**<code>GET</code>  /api/lists/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/GET_lists.md)
- [**<code>GET</code>  /api/lists/following/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/GET_lists_following.md)
- [**<code>GET</code>  /api/lists/:list_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/GET_lists_id.md)
- [**<code>GET</code> /api/lists/:list_id/clips/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/GET_lists_id_clips.md)
- [**<code>GET</code>  /api/lists/:list_id/relationship/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/GET_lists_id_relationship.md)
- [**<code>PUT</code>  /api/lists/:list_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/PUT_lists_id.md)
- [**<code>POST</code> /api/lists/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/POST_lists.md)
- [**<code>POST</code> /api/lists/:list_id/relationship/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/POST_lists_id_relationship.md)
- [**<code>DELETE</code>   /api/lists/:list_id/**](https://github.com/kippt/api-documentation/blob/master/endpoints/lists/DELETE_lists_id.md)

### Notifications

- [**<code>GET</code>  /api/notifications/**](https://github.com/kippt/api-documentation/blob/master/endpoints/notifications/GET_notifications.md)
- [**<code>POST</code> /api/notifications/**](https://github.com/kippt/api-documentation/blob/master/endpoints/notifications/POST_notifications.md)

## Objects

- [**User**](https://github.com/kippt/api-documentation/blob/master/objects/user.md)
- [**Clip**](https://github.com/kippt/api-documentation/blob/master/objects/clip.md)
- [**List**](https://github.com/kippt/api-documentation/blob/master/objects/list.md)
- [**Comment**](https://github.com/kippt/api-documentation/blob/master/objects/comment.md)
- [**Notification**](https://github.com/kippt/api-documentation/blob/master/objects/notification.md)

## Contribution

While designing Kippt's API, we looked how other well designed APIs are build and structured. 

- [Instagram](http://instagram.com/developer/) - Instagram's API has extremely well designed social API with following, comments and likes. Social structure in Kippt's API is heavily influenced by Instagram
- [GitHub](http://developer.github.com/) - GitHub's API is one of the few which can be navigated with textual identifiers which makes linking of the API and the web frontend possible
- [Foursquare](https://developer.foursquare.com/) - Foursquare uses timestamp based API versioning. So do we (v1 style versioning feels like boxed software).
- [500px](https://github.com/500px/api-documentation/) - This API documentation borrows heavily from 500px's structure
- [django-tastypie](http://tastypieapi.org/) - Kippt's pagination design is borrowed from Tastypie

