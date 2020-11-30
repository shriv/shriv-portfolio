---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Natural experiments for online behaviours"
summary: ""
authors: []
tags: []
categories: []
date: 2020-11-30T21:26:06+13:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

A common problem for websites and web-based technologies is understanding the impact of changes on user behaviour. The Randomised Control Trial (RCT), also referred to as A/B testing, is the gold standard framework for estimating impact. However, setting up A/B tests can be challenging for all types of changes or for embedded  and third party services. 

One avenue for learning about impact is adapting channel attribution methodologies from marketing. Attribution analysis was designed for the combined media advertising where the television or paper ad cannot be easily exposed as variants for the viewers. The power of the analysis comes instead from the acknowledgement that exposure impact can be measured from pathways to the desired outcome. For example, if the newspaper ad better connected to a final outcome of buying tickets to a movie, it would have a higher attribution. Of course, the key purpose of this approach was to attribute revenue to the different advertising approaches. 

Reducing pathways to a desired outcome simplifies the problem of impact analysis to the effect of an individual element on the final goal. This perspective works well for web browsing networks. The impact of new items or items with "enhanced features" can be seen by calculating their _contribution to the final goal_ - which is typically purchase on the site. 

![](description-methood.png)

While this methodology is not robust like causal methodologies, it is a valuable tool to gain _some_ insight from a natural, real-world experiment when the alternative is no insight of impact. 
