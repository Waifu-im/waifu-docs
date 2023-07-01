# Rate Limit

{% hint style="info" %}
This rate limit only applies to the `api.waifu.im` domain.
{% endhint %}

The rate limit is **1** request every **200** milliseconds. If you exceed this limit, the request will be put in a queue (with a maximum size of **10**).

If the queue is full, the server will respond with a **429** status code.

You can check the `Retry-After` header to get the time to wait (in seconds) before making another request.
