# Report

## Reports an image.

<mark style="color:green;">`POST`</mark> `https://api.waifu.im/report`

Used to report any inappropriate, offensive or wrongly labelled image in the API.

Requires `report` permission.

#### Headers

| Name                                            | Type   | Description                                 |
| ----------------------------------------------- | ------ | ------------------------------------------- |
| Authorization<mark style="color:red;">\*</mark> | string | `Bearer` followed by a space and your token |

#### Request Body

| Name                                        | Type    | Description                                                            |
| ------------------------------------------- | ------- | ---------------------------------------------------------------------- |
| image\_id<mark style="color:red;">\*</mark> | integer | The ID of the image to report.                                         |
| description                                 | string  | A brief explanation (up to 200 characters) used to describe the issue. |

{% tabs %}
{% tab title="200: OK " %}
```json
{
  "author_id": "428346579283272370",
  "description": "The tag 'maid' does not suit the image.",
  "existed": false,
  "image_id": 8008
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

{% hint style="warning" %}
If the image was already reported the `existed` key will be `true.`
{% endhint %}

{% tabs %}
{% tab title="Curl" %}
```sh
curl -X POST \
  'https://api.waifu.im/report' \
  -H 'Content-Type: application/json' \
  -H 'Accept-Version: v5' \
  -H 'Authorization: Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0' \
  -d '{
    "image_id": 8008,
    "description": "The tag '\''maid'\'' does not suit the image."
  }'

```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/report'

headers = {
    'Accept-Version': 'v5',
    'Authorization': 'Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0',
    'Content-Type': 'application/json',
}

data = {
    'image_id': 8008,
    'description': "The tag 'maid' does not suit the image."
}

response = requests.post(url, headers=headers, json=data)

if response.status_code == 200:
    data = response.json()
    # Process the response data as needed
else:
    print('Request failed with status code:', response.status_code)

```
{% endtab %}

{% tab title="Javascript" %}
```javascript
const apiUrl = 'https://api.waifu.im/report';

const headers = new Headers();
headers.append('Accept-Version', 'v5');
headers.append('Authorization', 'Bearer TjBY0MBcS3-SEc3Ms6T4GKjHGJkbqM6McejlQdnqo2y47jWNLa4agsWYdJukocDqHpm2zYFO5z2AjMzkUSfLsCz1AgbDhSjKLMIOnhJGFgODgOkSnzaAWzvGZZPdbm6vOTxs2chmz-3DSRVzwQLl__eYE4Wnjtr0aIGzXlo82M0');
headers.append('Content-Type', 'application/json');

const data = {
  image_id: 8008,
  description: "The tag 'maid' does not suit the image.",
};

fetch(apiUrl, {
  method: 'POST',
  headers: headers,
  body: JSON.stringify(data)
})
  .then(response => {
    if (response.ok) {
      return response.json();
    } else {
      throw new Error('Request failed with status code: ' + response.status);
    }
  })
  .then(data => {
    console.log(data);
    // Process the response data as needed
  })
  .catch(error => {
    console.error('An error occurred:', error.message);
  });

```
{% endtab %}
{% endtabs %}
