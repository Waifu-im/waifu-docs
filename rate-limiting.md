# Rate Limiting

{% hint style="info" %}
Rate limiting only applies to the `api.waifu.im` domain.
{% endhint %}

Rate limiting is currently set to **1** request every **200** milliseconds. If you exceed this limit, the request will be put in a queue (with a maximum size of **10**).

If the queue is full, the server will respond with a **429** status code.

You can check the `Retry-After` header to get the time to wait (in seconds) before making another request.

{% hint style="warning" %}
Please note that excessive and abusive use of the API can result in being blacklisted and firewall banned.

Please note that reaching the point of blacklisting requires persistent and excessive violations of the rate limits. Normal usage or occasional bursts of requests within a reasonable range will not trigger such actions.
{% endhint %}
