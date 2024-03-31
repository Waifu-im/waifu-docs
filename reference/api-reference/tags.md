# Tags

## Get tags

## Get all the tags available.

<mark style="color:blue;">`GET`</mark> `https://api.waifu.im/tags`

#### Query Parameters

| Name | Type    | Description                                                     |
| ---- | ------- | --------------------------------------------------------------- |
| full | boolean | Returns more information about the tags, such as a description. |

{% tabs %}
{% tab title="200: OK without full" %}
```json
{
  "versatile": [
    "maid",
    "waifu",
    "marin-kitagawa",
    "mori-calliope",
    "raiden-shogun",
    "oppai",
    "selfies",
    "uniform",
    "kamisato-ayaka"
  ],
  "nsfw": [
    "ass",
    "hentai",
    "milf",
    "oral",
    "paizuri",
    "ecchi",
    "ero"
  ]
}
```
{% endtab %}

{% tab title="200: OK with full" %}
```json
{
  "versatile": [
    {
      "tag_id": 13,
      "name": "maid",
      "description": "Cute womans or girl employed to do domestic work in their working uniform.",
      "is_nsfw": false
    },
    {
      "tag_id": 12,
      "name": "waifu",
      "description": "A female anime/manga character.",
      "is_nsfw": false
    },
    {
      "tag_id": 5,
      "name": "marin-kitagawa",
      "description": "One of two main protagonists (alongside Wakana Gojo) in the anime and manga series My Dress-Up Darling.",
      "is_nsfw": false
    },
    {
      "tag_id": 14,
      "name": "mori-calliope",
      "description": "Mori Calliope is an English Virtual YouTuber (VTuber) associated with hololive as part of its first-generation English branch of Vtubers.",
      "is_nsfw": false
    },
    {
      "tag_id": 15,
      "name": "raiden-shogun",
      "description": "Genshin Impact's Raiden Shogun is a fierce lady in the Genshin ranks.",
      "is_nsfw": false
    },
    {
      "tag_id": 7,
      "name": "oppai",
      "description": "Girls with large breasts",
      "is_nsfw": false
    },
    {
      "tag_id": 10,
      "name": "selfies",
      "description": "A photo-like image of a waifu.",
      "is_nsfw": false
    },
    {
      "tag_id": 11,
      "name": "uniform",
      "description": "Girls wearing any kind of uniform, cosplay etc... ",
      "is_nsfw": false
    },
    {
      "tag_id": 17,
      "name": "kamisato-ayaka",
      "description": "Kamisato Ayaka is a playable Cryo character in Genshin Impact.",
      "is_nsfw": false
    }
  ],
  "nsfw": [
    {
      "tag_id": 1,
      "name": "ass",
      "description": "Girls with a large butt. ",
      "is_nsfw": true
    },
    {
      "tag_id": 4,
      "name": "hentai",
      "description": "Explicit sexual content.",
      "is_nsfw": true
    },
    {
      "tag_id": 6,
      "name": "milf",
      "description": "A sexually attractive middle-aged woman.",
      "is_nsfw": true
    },
    {
      "tag_id": 8,
      "name": "oral",
      "description": "Oral sex content.",
      "is_nsfw": true
    },
    {
      "tag_id": 9,
      "name": "paizuri",
      "description": "A subcategory of hentai that involves breast sex, also known as titty fucking.",
      "is_nsfw": true
    },
    {
      "tag_id": 2,
      "name": "ecchi",
      "description": "Slightly explicit sexual content. Show full to partial nudity. Doesn't show any genital.",
      "is_nsfw": true
    },
    {
      "tag_id": 3,
      "name": "ero",
      "description": "Any kind of erotic content, basically any nsfw image.",
      "is_nsfw": true
    }
  ]
}
```
{% endtab %}

{% tab title="400: Bad Request " %}
```json
{"detail":"Bad Request"}
```
{% endtab %}

{% tab title="401: Unauthorized " %}
```json
{"detail":"Unauthorized"}
```
{% endtab %}

{% tab title="403: Forbidden " %}
```json
{"detail":"Forbidden"}
```
{% endtab %}

{% tab title="404: Not Found " %}
```json
{"detail":"Not Found"}
```
{% endtab %}

{% tab title="500: Internal Server Error " %}
```json
{"detail":"Internal Server Error"}
```
{% endtab %}
{% endtabs %}

Here is an example to get a list of all the tags available:

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X GET \
  'https://api.waifu.im/tags'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/tags'

response = requests.get(url)

if response.status_code == 200:
    data = response.json()
    # Process the response data as needed
else:
    print('Request failed with status code:', response.status_code)

```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const apiUrl = 'https://api.waifu.im/tags';

fetch(apiUrl)
  .then(response => {
    if (response.ok) {
      return response.json();
    } else {
      throw new Error('Request failed with status code: ' + response.status);
    }
  })
  .then(data => {
    // Process the response data as needed
    console.log(data);
  })
  .catch(error => {
    console.error('An error occurred:', error.message);
  });

```
{% endtab %}
{% endtabs %}
