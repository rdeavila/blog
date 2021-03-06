# armno.in.th

[![Netlify Status](https://api.netlify.com/api/v1/badges/7d34a977-d95b-4b64-9e99-1a1df43ee944/deploy-status)](https://app.netlify.com/sites/armno/deploys)

My [blog](https://armno.in.th). Built with [Hugo](https://gohugo.io/). Migrated from [`armno/armno.github.io`](https://github.com/armno/armno.github.io).

## Development

```sh
$ hugo serve -D
```

## Create a new post

```sh
$ hugo new post/<post-title>/index.md
```

---

## **New!** - `image` shortcode

A shortcode to insert responsive, lazy-loaded images into post content.

```
{{< image
  src="images/platoo.jpg"
  alt="test"
  ratio="16-9"
  caption="caption to display below the picture"
>}}
```

## `picture-lazy` shortcode for lazy-loaded pictures

attributes:

- `wrapper-class`
- `src`
- `alt`
- `ratio`
- `caption`

```
{{< picture-lazy
  wrapper-class="semi-full"
  src="images/platoo.jpg"
  alt="test"
  ratio="16-9"
  caption="caption to display below the picture"
>}}
```

`ratio` attribute can be set for a lazily-loaded image to [perserve vertical space](https://github.com/verlok/lazyload#occupy-vertical-space-and-maintain-ratio) and prevent page jumps when the image is loaded.

supported `ratio` values

- `16-10`
- `16-9`
- `4-3`
- `3-2`
- `1-1`

for images that have different aspect ration, `ratio` attribute should be omitted. page jumping is still better than content overlapping or too much space below the image.

better crop images to one of the support ratio :)

output:

```html
<figure class="media lazy-wrapper semi-full ratio ratio-16-9">
  <img class="lazy" data-src="images/platoo.jpg" alt="test">
  <noscript>
    <img src="images/platoo.jpg" alt="test">
  </noscript>
  <figcaption class="media-caption">Test</figcaption>
</figure>
```

## `picture` shortcode

attributes:

- `wrapper-class`: CSS class(or classes) for the wrapper element of the image (`<p>`).
- `img-class`: CSS class(or classes) for the `<img>` itself.
- `src`
- `alt`
- `caption`

```
{{< picture
  wrapper-class="semi-full"
  img-class="nom"
  src="images/platoo.jpg"
  alt="test"
  caption="image caption"
>}}
```

output:

```html
<figure class="media semi-full">
  <img class="nom" src="images/platoo.jpg" alt="test">
  <figcaption class="media-caption">image caption</figcaption>
</figure>
```
