# Quick Start

{% hint style="info" %}
This small tutorial will only provide you with minimal knowledge of the API, if you wish to apply filters etc, please refere to the API Reference
{% endhint %}

## Get a random image

The easiest and most common way to use the API is to get a random waifu images.

{% swagger method="get" path="search" baseUrl="https://api.waifu.im/" summary="Search Images" expanded="true" %}
{% swagger-description %}
Retrieves images randomly or by tag based on the specified search criteria.
{% endswagger-description %}

{% swagger-parameter in="query" required="false" name="included_tags" type="Array[string]" %}
Force the API to return images with at least all the provided tags.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="excluded_tags" type="Array[string]" %}
Force the API to return images without any of the provided tags.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="included_files" type="Array[string]" %}
Force the API to provide only the specified file IDs or signatures.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="excluded_files" type="Array[string]" %}
Force the API to not list the specified file IDs or signatures.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="is_nsfw" type="string" enum=["null", "true", "false"] %}
Force or exclude lewd files (only works if included_tags only contain versatile tags and no nsfw only tag). You can provide 'null' to make it random.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="gif" type="boolean" %}
Force or prevent the API to return .gif files.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="order_by" type="string" enum=["FAVORITES", "UPLOADED_AT", "LIKED_AT", "RANDOM"] %}
Ordering criteria for the images.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="orientation" type="string" enum=["LANDSCAPE", "PORTRAIT", "RANDOM"] %}
Image orientation criteria.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="many" type="boolean" %}
Return an array of 30 files if true.
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="full" type="boolean" %}
Returns the full result without any limit (admins only).
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="width" type="string" example=">=2000" %}
Filter images by width (in pixels). Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="height" type="string" example=">=2000" %}
Filter images by height (in pixels). Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="byte_size" type="string" example=">=2000" %}
Filter images by byte size. Accepted operators: <=, >=, >, <, !=, =
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
  "images": [
    {
      "artist": {
        "artist_id": 1,
        "deviant_art": "https://www.deviantart.com/4thwallzart",
        "name": "fourthwallzart",
        "patreon": "string",
        "pixiv": "string",
        "twitter": "https://twitter.com/4thWallzArt"
      },
      "byte_size": 3299586,
      "dominant_color": "#bbb7b2",
      "extension": ".png",
      "favorites": 1,
      "height": 2304,
      "image_id": 8108,
      "is_nsfw": false,
      "liked_at": "string",
      "preview_url": "https://www.waifu.im/preview/8108/",
      "signature": "58e6f0372364abda",
      "source": "https://www.patreon.com/posts/persephone-78224476",
      "tags": [
        {
          "description": "A female anime/manga character.",
          "is_nsfw": false,
          "name": "waifu",
          "tag_id": 12
        }
      ],
      "uploaded_at": "2023-05-03T18:40:04.381354+02:00",
      "url": "https://cdn.waifu.im/8108.png",
      "width": 1536
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

Example:
