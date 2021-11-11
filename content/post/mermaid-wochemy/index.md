---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Mermaid in wowchemy sites"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-11-11T17:04:07+13:00
lastmod: 2021-11-11T17:04:07+13:00
featured: false
draft: false
toc: true

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## Mermaid diagrams for wowchemy sites
According to the [instructions on wowchemy docs](https://wowchemy.com/docs/content/writing-markdown-latex/#diagrams), it's quite easy to include mermaid diagrams. Just need to change the `diagram` parameter in `config/params.toml` to `true`. With this change, the diagram is rendered when the code is within a mermaid code block (using simple backticks markup). 


## Default version of Mermaid in wowchemy is problematic
Unfortunately, I had some issues with this approach. Wowchemy is still using `mermaid 8.8.4` as seen in the [js plugin list](https://github.com/wowchemy/wowchemy-hugo-themes/blob/0d97991430036417584e1c951bc58c434ccbf1a3/wowchemy/data/assets.toml#L59). The main issue being that the current version is `8.13.0` and features like rendering `flowcharts` with different directions to `subgraphs` are not available. A secondary issue was slowness in the render. Perhaps, it was my poor internet but the diagrams wouldn't always render with the default plugin location. 


## How to us the latest / custom version of mermaid
I ended up abandoning the wowchemy native approach and using [mermaid as a third party plugin](https://wowchemy.com/docs/hugo-tutorials/extending-wowchemy/#add-scripts-js). Following instructions from [here](https://skeptric.com/diagrams-in-hugo/#implementation), I copied in the JS script reference to `layouts/partials/custom_js.html` and the shortcodes to `layouts/shortcodes/mermaid.html`. 

Mermaid can now be called within the shortcode - opened with `{{< mermaid align="left" theme="neutral" >}}` and closed as `{{< /mermaid >}}`. And flowcharts with different direction to the subgraphs can be easily rendered. 

{{< mermaid align="left" theme="neutral" >}}
flowchart LR
	
	subgraph EXTRACT
		direction TB
			oi[Outlook inbox] --> |Download manually|gs[Get and save data]
			gs --> |Rename file <br> change column types|rd[Raw data store]
	end
	
	subgraph TRANSFORM
		direction TB
            e[Raw data store] -->|Manual filename change| sas_read
			sas_read[Read raw data <br> into SAS format] --> |Manual filename change| sas_trans[Transform data]
			sas_trans --> data[Processed data]
	end

fa[feed A] -->|automated <br> delivery| EXTRACT --> TRANSFORM 
{{< /mermaid >}}