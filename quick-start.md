# Quick Start

{% hint style="info" %}
This small tutorial will only provide you with minimal knowledge of the API, if you wish to apply filters etc, please refere to the API Reference
{% endhint %}

## Get a random image

The easiest and most common way to use the API is to get a random waifu images.

{% swagger method="get" path="search" baseUrl="https://api.waifu.im/" summary="" expanded="true" fullWidth="false" %}
{% swagger-description %}
Get a waifu pictures based on specifc criterias or randomly.
{% endswagger-description %}

{% swagger-parameter in="query" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" required="false" name="included_tags" type="Array[string]" %}
Force the API to return images with at least all the provided tags
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
