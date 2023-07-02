# Report

{% swagger method="post" path="report" baseUrl="https://api.waifu.im/" summary="Reports an image" %}
{% swagger-description %}
Used to report any inappropriate, offensive or wrongly labelled image in the API.

Requires `report` permission.
{% endswagger-description %}

{% swagger-parameter in="body" name="image_id" type="integer" required="true" %}
The ID of the image to report.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="string" required="false" %}
A brief explanation (up to 200 characters) used to describe the issue.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="string" %}
`Bearer`

 (with the space) followed by your token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "author_id": 428346579283272370,
  "description": "The tag 'maid' does not suit the image.",
  "existed": false,
  "image_id": 8008
}
```
{% endswagger-response %}

{% swagger-response status="400: Bad Request" description="" %}
```json
{"detail":"Bad Request"}
```
{% endswagger-response %}

{% swagger-response status="401: Unauthorized" description="" %}
```json
{"detail":"Unauthorized"}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{"detail":"Forbidden"}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json
{"detail":"Not Found"}
```
{% endswagger-response %}

{% swagger-response status="500: Internal Server Error" description="" %}
```json
{"detail":"Internal Server Error"}
```
{% endswagger-response %}
{% endswagger %}
