# Tags

Images are classified by a tag system and can have multiple tags!

There are versatile tags that can describe both safe and lewd images, as well as nsfw tags that only describe lewd images.

A mistake people usually make is that they assume nsfw tags are lewd and versatile are safe, but thats not true at all. When you make a request and add a versatile tag into `included_tags` the API will return all safe image with that tag, since by default the API returns only safe image. However, if you provide a versatile tag and pass the `is_nsfw` parameter to true then the API will returns every nsfw image with that tag.

Finally nsfw tag will always return lewd images regardless of `is_nsfw` parameter.

{% tabs %}
{% tab title="Versatile" %}
* [waifu](https://api.waifu.im/search?included\_tags=waifu)
{% endtab %}

{% tab title="NSFW" %}
* [ero](https://api.waifu.im/searhc?included\_tags=ero)
{% endtab %}
{% endtabs %}

You can get a list of all tags at the [tags.md](reference/api-reference/tags.md "mention") endpoint.
