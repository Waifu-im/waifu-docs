# Authorization

By default, when using your own authentication token, you have all permissions available. However, it's possible to grant specific permissions to other users on your account or 'ask' people to grant you permissions by the same process. This allows you to perform certain actions on their behalf, based on the granted permissions. this may be useful to create an app to allow user to add image to their favorites for example.

The following route isnt part of the API but is more like a functionality of the website.

{% swagger method="get" path="authorization" baseUrl="https://www.waifu.im/" summary="Prompt a user to give you permissions on their account" %}
{% swagger-description %}
The person that consult the page and click on 

`Authorize`

 will grant permissions over their account
{% endswagger-description %}

{% swagger-parameter in="query" name="user_id" type="Integer" required="true" %}
The discord user ID of the user that will receive the permissions
{% endswagger-parameter %}

{% swagger-parameter in="query" name="permissions" type="String" required="true" %}
The permissions that will be asked for. Available permissions are 

`view_favorites`

 and 

`manage_favorites`
{% endswagger-parameter %}
{% endswagger %}

\
\
