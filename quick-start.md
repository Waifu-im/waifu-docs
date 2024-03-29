# Quick Start

{% hint style="info" %}
This small tutorial will only provide you with minimal knowledge of the API, if you wish to learn more just continue reading the docs step by step
{% endhint %}

{% hint style="info" %}
Alternatively you can also use one of the packages mentioned in [#packages](resources.md#packages "mention")
{% endhint %}

## Get a random image

The easiest and most common way to use the API is to get a random waifu images.

Here is an example to get a random image with the `raiden-shogun` and `maid` tags with an height superior or equal to 2000 pixels:

{% tabs %}
{% tab title="Curl" %}
```bash
curl -X GET \
  'https://api.waifu.im/search?included_tags=raiden-shogun&included_tags=maid&height=>=2000' \
  -H 'Content-Type: application/json'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/search'
params = {
    'included_tags': ['raiden-shogun', 'maid'],
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
  included_tags: ['raiden-shogun', 'maid'],
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

{% hint style="success" %}
It is recommended to checkout the [api-reference](reference/api-reference/ "mention").

You can find a more detailed guide for this route here : [#search-images.](reference/api-reference/search.md#search-images. "mention")
{% endhint %}
