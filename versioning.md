# Versioning

Versioning is crucial for maintaining stability, flexibility, and smooth transitions in an API's evolution. By utilizing versioning, you can ensure that changes and updates to the API do not disrupt existing integrations or cause unexpected errors for your users.

To make use of our API versioning, you need to include the desired version in the `Accept-Version` header of your API requests. This header allows you to explicitly specify the version of the API you want to interact with, ensuring that your code remains compatible and predictable, even as newer versions become available.

{% hint style="info" %}
The current version of the API is v5


{% endhint %}

{% tabs %}
{% tab title="Curl" %}
```
curl -X GET \
  'https://api.waifu.im/search' \
  -H 'Content-Type: application/json' \
  -H 'Accept-Version: v5'
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = 'https://api.waifu.im/search'

headers = {
    'Accept-Version': 'v5'
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
const apiUrl = 'https://api.waifu.im/search';

const headers = new Headers();
headers.append('Accept-Version', 'v5');

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
