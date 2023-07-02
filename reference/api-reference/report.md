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
  "existed": true,
  "image_id": 8008
}
```
{% endswagger-response %}
{% endswagger %}
