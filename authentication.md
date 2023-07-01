# Authentication

Some routes in our API require authentication to ensure secure access to user-specific resources. To authenticate your requests, you need to obtain an authentication token. Follow the steps below to generate your token.

## Generating a Token

1. Visit your [dashboard](https://www.waifu.im/dashboard/).
2. Log in using your discord credentials or create a new account if you don't have one.
3. Copy your token and securely store it. Treat your token like a password and do not share it with anyone.

### Accessing Authorized Routes

here is an example to [#get-your-favorites](reference/api-reference/favorites.md#get-your-favorites "mention")

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
