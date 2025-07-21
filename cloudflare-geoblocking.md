---
icon: triangle-exclamation
---

# Cloudflare GeoBlocking

Due to repeated abuse and a recent DDoS attack originating from specific regions, requests from certain countries are now subject to Cloudflare's managed challenge. This helps protect the stability and reliability of the API for all users.

If you're affected and require access, you can request a personal geo-blocking bypass key. To do so:

1. Log in at [https://www.waifu.im/dashboard/](https://www.waifu.im/dashboard/) using your Discord account.
2. Display your **API token** (it is automatically generated if you do not already have one).
3. Email your token to [**geobypass@waifu.im**](mailto:geobypass@waifu.im) with a small message explaining that you are affected.
4. You will receive a personal `x-geo-blocking-bypass` key linked to your account.
5. **After receiving the bypass key, immediately regenerate your API token** to ensure security.

Include the bypass key in the `x-geo-blocking-bypass` header for all API requests.

{% hint style="danger" %}
**Important:** This key is strictly personal. Sharing it or using it for abusive purposes will result in revocation.
{% endhint %}

