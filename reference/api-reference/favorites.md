# Favorites

## Get your favorites

{% swagger method="get" path="/fav" baseUrl="https://api.waifu.im" summary="Get your favorites" %}
{% swagger-description %}
Requires 

`view_favorites`

 permission.
{% endswagger-description %}

{% swagger-parameter in="query" required="false" name="included_tags" type="array[string]" %}
Force the API to return images with at least all the provided tags.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="excluded_tags" type="array[string]" %}
Force the API to return images without any of the provided tags.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="included_files" type="array[string]" %}
Force the API to provide only the specified file IDs or signatures.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="excluded_files" type="array[string]" %}
Force the API to not list the specified file IDs or signatures.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="is_nsfw" type="string" %}
Force or exclude lewd files (only works if included_tags only contain versatile tags and no nsfw only tag). You can provide 'null' to make it random.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="gif" type="boolean" %}
Force or prevent the API to return .gif files.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="order_by" type="string" %}
Ordering criteria for the images.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="orientation" type="string" %}
Image orientation criteria.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="many" type="boolean" %}
Return an array of 30 files if true.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="full" type="boolean" %}
Returns the full result without any limit (admins only).
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="width" type="string" %}
Filter images by width (in pixels). Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="height" type="string" %}
Filter images by height (in pixels). Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="byte_size" type="string" %}
Filter images by byte size. Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" type="string" %}
`Bearer`

 (with the space) followed by your token
{% endswagger-parameter %}
{% endswagger %}

## Manage your favorites

{% swagger src="https://petstore.swagger.io/v2/swagger.json" path="/user/createWithList" method="post" %}
[https://petstore.swagger.io/v2/swagger.json](https://petstore.swagger.io/v2/swagger.json)
{% endswagger %}

{% swagger src="https://petstore.swagger.io/v2/swagger.json" path="/user/createWithArray" method="post" %}
[https://petstore.swagger.io/v2/swagger.json](https://petstore.swagger.io/v2/swagger.json)
{% endswagger %}
