+++
title = "Components"
date = "2022-10-20"
description = "The Kita theme components."
[taxonomies]
tags = ["markdown", "css", "html"]
[extra]
mermaid = true
+++

The Kita theme provides multiple Tera components.

Zola 0.23 replaced shortcodes with components. See [Zola documentation](https://www.getzola.org/documentation/content/overview/#migrating-from-shortcodes) for more information.

## Mermaid

To use Mermaid in your page, you have to set `extra.mermaid = true` in the frontmatter of page.

{% raw %}

```markdown
+++
title = "Your page title"

[extra]
mermaid = true
+++
```

{% endraw %}

Then you can use the `mermaid` component like:

{% raw %}

```markdown
{% <mermaid> %}

graph TD;
A-->B;
A-->C;
B-->D;
C-->D;

{% </mermaid> %}
```

{% endraw %}

This will be rendered as:

{% <mermaid> %}

graph TD;
A-->B;
A-->C;
B-->D;
C-->D;

{% </mermaid> %}

In addition, you can use code block inside `mermaid` component and the code block will be ignored.

The code block prevents formatter from breaking mermaid's formatting.

{% raw %}

````markdown
{% <mermaid> %}

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

{% </mermaid> %}
````

{% endraw %}

This will be rendered as:

{% <mermaid> %}

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

{% </mermaid> %}

## Admonition

The `admonition` component displays a banner to help you put notice in your page.

This is another way to write a GitHub-style alert, but it supports custom titles.

You can use the `admonition` component like:

{% raw %}

```markdown
{% <admonition type="note" title="note"> %}
The `note` admonition.
{% </admonition> %}
```

{% endraw %}

{% <admonition type="note" title="note"> %}
The `note` admonition.
{% </admonition> %}

{% <admonition type="tip" title="tip"> %}
The `tip` admonition.
{% </admonition> %}

{% <admonition type="important" title="important"> %}
The `important` admonition.
{% </admonition> %}

{% <admonition type="warning" title="warning"> %}
The `warning` admonition.
{% </admonition> %}

{% <admonition type="caution" title="caution"> %}
The `caution` admonition.
{% </admonition> %}

## Gallery

The `gallery` component is very simple html-only clickable picture gallery that displays all images from the page assets.

It's from [Zola documentation](https://www.getzola.org/documentation/content/image-processing/)

{% raw %}

```markdown
{{<gallery />}}
```

{% endraw %}

{{<gallery />}}

## Inline SVG

The `inline_svg` component is used to embed SVG images directly into a webpage, rather than including them via an `<img>` tag.

You can use the `inline_svg` component like:

{% raw %}

```markdown
{% <inline_svg> %}
![Van de Graaf canon](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}
```

{% endraw %}

{% <inline_svg> %}
![Van de Graaf canon](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}

If you don't want to display a caption below the image, you can set the Markdown image `alt` text to an empty string, `Inline SVG`, `inline-svg`, or `inline_svg`.

{% raw %}

```markdown
{% <inline_svg> %}
![](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}

{% <inline_svg> %}
![Inline SVG](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}

{% <inline_svg> %}
![inline-svg](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}

{% <inline_svg> %}
![inline_svg](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}
```

{% endraw %}

{% <inline_svg> %}
![Inline SVG](Van_de_Graaf_canon_in_book_design.svg)
{% </inline_svg> %}
