+++
title = "Shortcodes"
date = "2022-10-20"
description = "The Kita theme shortcodes."
[taxonomies]
tags = ["markdown", "css", "html"]
[extra]
mermaid = true
+++

The Kita theme providers multiple shortcodes.

Never heard of shortcodes? See [Zola documentation](https://www.getzola.org/documentation/content/shortcodes/) for more information.

## Mermaid

To use Mermaid in your page, you have to set `extra.mermaid = true` in the frontmatter of page.

```markdown
+++
title = "Your page title"

[extra]
mermaid = true
+++
```

Then you can use the `mermaid()` shortcodes like:

```markdown
{%/* mermaid() */%}

graph TD;
A-->B;
A-->C;
B-->D;
C-->D;

{%/* end */%}
```

This will be rendered as:

{% mermaid() %}

graph TD;
A-->B;
A-->C;
B-->D;
C-->D;

{% end %}

In addition, you can use code block inside `mermaid()` shortcodes and the code block will be ignored.

The code block prevents formatter from breaking mermaid's formatting.

````markdown
{%/* mermaid() */%}

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

{%/* end */%}
````

This will be rendered as:

{% mermaid() %}

```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```

{% end %}

## Admonition

The `admonition()` shortcode displays a banner to help you put notice in your page.

This is another way to write a GitHub-style alert, but it supports custom titles.

You can use the `admonition()` shortcode like:

```markdown
{%/* admonition(type="note", title="note") */%}
The `note` admonition.
{%/* end */%}
```

{% admonition(type="note", title="note") %}
The `note` admonition.
{% end %}

{% admonition(type="tip", title="tip") %}
The `tip` admonition.
{% end %}

{% admonition(type="important", title="important") %}
The `important` admonition.
{% end %}

{% admonition(type="warning", title="warning") %}
The `warning` admonition.
{% end %}

{% admonition(type="caution", title="caution") %}
The `caution` admonition.
{% end %}

## Gallery

The `gallery()` shortcode is very simple html-only clickable picture gallery that displays all images from the page assets.

It's from [Zola documentation](https://www.getzola.org/documentation/content/image-processing/)

```markdown
{{/* gallery() */}}
```

{{ gallery() }}

## Inline SVG

The `inline_svg()` shortcode is used to embed SVG images directly into a webpage, rather than including them via an `<img>` tag.

You can use the `inline_svg()` shortcodes like:

```markdown
{%/* inline_svg() */%}
![Van de Graaf canon](Van_de_Graaf_canon_in_book_design.svg)
{%/* end */%}
```

{% inline_svg() %}
![Van de Graaf canon](Van_de_Graaf_canon_in_book_design.svg)
{% end %}

If you don't want to display a caption below the image, you can set the Markdown image `alt` text to an empty string, `Inline SVG`, `inline-svg`, or `inline_svg`.

```markdown
{%/* inline_svg() */%}
![](Van_de_Graaf_canon_in_book_design.svg)
{%/* end */%}

{%/* inline_svg() */%}
![Inline SVG](Van_de_Graaf_canon_in_book_design.svg)
{%/* end */%}

{%/* inline_svg() */%}
![inline-svg](Van_de_Graaf_canon_in_book_design.svg)
{%/* end */%}

{%/* inline_svg() */%}
![inline_svg](Van_de_Graaf_canon_in_book_design.svg)
{%/* end */%}
```

{% inline_svg() %}
![Inline SVG](Van_de_Graaf_canon_in_book_design.svg)
{% end %}
