# Favorites

## Get your favorites

{% hint style="warning" %}
This endpoint returns all images in the user favorites, meaning it will also returns lewd images if there are some in the user favorites.
{% endhint %}

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

{% swagger-response status="200: OK" description="" %}
```json
{
  "images": [
    {
      "signature": "85d7aa55941c7087",
      "extension": ".jpg",
      "image_id": 7622,
      "favorites": 3,
      "dominant_color": "#dfcdc5",
      "source": "https://www.pixiv.net/en/artworks/95981691",
      "artist": {
        "artist_id": 54,
        "name": "大熊まい",
        "patreon": null,
        "pixiv": "https://www.pixiv.net/users/29449",
        "twitter": "https://twitter.com/m_okuma0831",
        "deviant_art": null
      },
      "uploaded_at": "2022-04-07T13:51:47.979181Z",
      "liked_at": "2022-04-07T14:07:46.455245Z",
      "is_nsfw": false,
      "width": 1406,
      "height": 1875,
      "byte_size": 1538007,
      "url": "https://cdn.waifu.im/7622.jpg",
      "preview_url": "https://www.waifu.im/preview/7622/",
      "tags": [
        {
          "tag_id": 12,
          "name": "waifu",
          "description": "A female anime/manga character.",
          "is_nsfw": false
        }
      ]
    }
  ]
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

Here is an example to get your favorites:

{% tabs %}
{% tab title="Curl" %}
```
curl -X GET \
  'https://api.waifu.im/fav' \
  -H 'Accept-Version: v5' \
  -H 'Authorization: Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/fav'

headers = {
    'Accept-Version': 'v5',
    'Authorization': 'Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0',
}

response = requests.get(url, headers=headers)

if response.status_code == 200:
    data = response.json()
    # Process the response data as needed
else:
    print('Request failed with status code:', response.status_code)

```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const apiUrl = 'https://api.waifu.im/fav';

const headers = new Headers();
headers.append('Accept-Version', 'v5');
headers.append('Authorization', 'Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0');

fetch(apiUrl, { headers })
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

## Manage your favorites
