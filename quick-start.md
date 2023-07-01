# Quick Start

{% hint style="info" %}
This small tutorial will only provide you with minimal knowledge of the API, if you wish to apply filters etc, please refere to the API Reference
{% endhint %}

## Get a random image

The easiest way and most common to use the API is to get a random waifu images.

{% swagger src=".gitbook/assets/swagger.yaml" path="/search" method="get" expanded="false" %}
[swagger.yaml](.gitbook/assets/swagger.yaml)
{% endswagger %}

Example:

{% tabs %}
{% tab title="curl" %}
```
curl https://api.myapi.com/v1/pet  
    -u YOUR_API_KEY:  
    -d name='Wilson'  
    -d species='dog'  
    -d owner_id='sha7891bikojbkreuy'  
```
{% endtab %}

{% tab title="Python" %}
```python
// Set your API key before making the request
myapi.api_key = YOUR_API_KEY

myapi.Pet.create(
    name='Wilson',
    owner_id='sha7891bikojbkreuy',
    species='Dog',
    breed='Golden Retriever',
)
```
{% endtab %}
{% endtabs %}
