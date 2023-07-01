# Favorites

## Get your favorites

{% swagger method="get" path="/fav" baseUrl="https://api.waifu.im" summary="Get your favorites" %}
{% swagger-description %}
Requires 

`view_favorites`

 permission.
{% endswagger-description %}

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
