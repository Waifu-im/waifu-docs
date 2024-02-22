# Search

{% swagger method="get" path="search" baseUrl="https://api.waifu.im/" summary="Search images." expanded="true" %}
{% swagger-description %}
Retrieves images randomly or by tag based on the specified search criteria.
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
Force or exclude lewd files (only works if included\_tags only contain versatile tags and no nsfw only tag). You can provide 'null' to make it random.
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

{% swagger-parameter in="header" name="Authorization" type="string" required="false" %}
`Bearer` followed by a space and your token
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

Here is an example to get a random image with the `maid` tag with an height superior or equal to 2000 pixels:

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X GET \
  'https://api.waifu.im/search?included_tags=maid&height=>=2000' \
  -H 'Content-Type: application/json'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/search'
params = {
    'included_tags': ['maid'],
    'height': '>=2000'
}

response = requests.get(url, params=params)

if response.status_code == 200:
    data = response.json()
    # Process the response data as needed
else:
    print('Request failed with status code:', response.status_code)

```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const apiUrl = 'https://api.waifu.im/search';  // Replace with the actual API endpoint URL
const params = {
  included_tags: 'maid',
  height: '>=2000'
};

const queryParams = new URLSearchParams();

for (const key in params) {
  if (Array.isArray(params[key])) {
    params[key].forEach(value => {
      queryParams.append(key, value);
    });
  } else {
    queryParams.set(key, params[key]);
  }
}
const requestUrl = `${apiUrl}?${queryParams.toString()}`;

fetch(requestUrl)
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
