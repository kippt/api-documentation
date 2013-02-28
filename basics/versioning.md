# Versioning

Kippt's API uses custom mime types to specify the version. Instead of version numbers you need to provide the implementation date in format <code>YYYYMMDD</code>. API will return the right version for the requested date. There are times when we might need to make changes to the API and we'll use this version to provide backwards compatibility for a period of time if there's a need for that.

There are some endpoints and fields which are clearly marked as **experimental** or **unsupported** in the documentation. These are, as it says, unsupported and versioning work affect them: we might change them without prior notice but we try to avoid that. Use with caution.

Accepted mime types are:

- Latest: <code>application/json</code>
- Version: <code>application/vnd.kippt.YYYYMMDD+json</code>

You should also use <code>X-Kippt-Client</code> HTTP header with app's name, contact email and url. This makes it easy for us to contact you if there's a case for that (i.e. deprecated features).

Format: <code>curl -H "X-Kippt-Client: BookmarkingApp,contact@bookmarkingapp.com,http://bookmarkingapp.com"</code>