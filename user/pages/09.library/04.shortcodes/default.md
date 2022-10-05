---
title: Shortcodes
---
These Shortcodes come with this theme.

### caption

```md
[raw][caption class="image" caption="Quelle: Unsplash.com"]
![](image.jpg)
[/caption][/raw]
```

[caption class="image" caption="Quelle: Unsplash.com"]
![](../../_heros/farn.jpg)
[/caption]

Adds a caption (via HTML figure+figcaption) to your media (image, video, embed, audio).

## email

```md
[raw][email link=1]Chunkylover53@aol.com[/email][/raw]
```

[email link=1]Chunkylover53@aol.com[/email]

Mask E-Mails with HTML entities to give some spam protection. `link` parameter is optional and makes the address a `mailto` link.


## icon

```md
[raw][icon=mail title="E-Mail"][/raw]
```

[icon=mail title="E-Mail"]

Shortcode to use in text icons utilizing the [svg-extension](https://github.com/bitstarr/grav-plugin-svg-extension) plugin.

As seen in the example the first word is the icon name, optional parameters follow after that.

| Paramter | Effect |
| --- | --- |
| id | Set an ID for the SVG element |
| class | Set the CSS classes for the SVG element |
| title | Set a title (accessability) |


## lang

```md
[raw][lang=fr inline=1]Bonjour[/lang][/raw]
[raw][lang=es]
Hola!
[/lang][/raw]
```

[lang=fr inline=1]Bonjour[/lang]

[lang=es]
Hola!
[/lang]

Wrap text in a different language semantically, so screenreader can interpret and pronounce it correctly. By default it wraps the text in a `div`, adding the optional `inline` parameter wraps it in a `span`.

## video

```md
[raw][video=Uuad8V5f_QA]
[video="https://www.youtube.com/watch?v=Uuad8V5f_QA"]
[video id=Uuad8V5f_QA]
[video id="https://www.youtube.com/watch?v=Uuad8V5f_QA"]
[video id=141358 type=vimeo][/raw]
```

Embed a video from YouTube or Vimeo with a privacy alert. The video will only load (and request external resources) if the user affirms (once or for the whole site).

! This components CSS and JS need to be added to processing. They are not enabled by default.

## raw

```md
[raw][raw][email link=1]Chunkylover53@aol.com[/email][/raw][/raw]
```

This is a helper to show shortcodes in pages without getting them processed.