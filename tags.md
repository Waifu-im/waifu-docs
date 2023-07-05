# Tags

Images are classified by a tag system and can have multiple tags!

There are versatile tags that can describe both safe and lewd images, as well as nsfw tags that only describe lewd images.

If you make a request and add a versatile tag into `included_tags` the API will return all safe image with that tag, since by default the API returns only safe image.

If you provide a versatile tag and pass the `is_nsfw` parameter to `true` then the API will returns every nsfw image with that tag.

Nsfw tags will always return lewd images regardless of `is_nsfw` parameter.



Here are the tags available.

{% tabs %}
{% tab title="Versatile" %}
* [waifu](https://api.waifu.im/search?included\_tags=waifu)
* [maid](https://api.waifu.im/search?included\_tags=maid)
* [marin-kitagawa](https://api.waifu.im/search?included\_tags=marin-kitagawa)
* [mori-calliope](https://api.waifu.im/search?included\_tags=mori-calliope)
* [raiden-shogun](https://api.waifu.im/search?included\_tags=raiden-shogun)
* [oppai](https://api.waifu.im/search?included\_tags=oppai)
* [selfies](https://api.waifu.im/search?included\_tags=selfies)
* [uniform](https://api.waifu.im/search?included\_tags=uniform)
{% endtab %}

{% tab title="NSFW" %}
* [ero](https://api.waifu.im/search?included\_tags=ero)
* [ass](https://api.waifu.im/search?included\_tags=ass)
* [hentai](https://api.waifu.im/search?included\_tags=hentai)
* [milf](https://api.waifu.im/search?included\_tags=milf)
* [oral](https://api.waifu.im/search?included\_tags=oral)
* [paizuri](https://api.waifu.im/search?included\_tags=paizuri)
* [ecchi](https://api.waifu.im/search?included\_tags=ecchi)
{% endtab %}
{% endtabs %}

From the API, you can get a list of all tags at the [tags.md](reference/api-reference/tags.md "mention") endpoint.
