---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Shipping Schedules"
summary: ""
authors: []
tags: []
categories: []
date: 2023-01-25T11:51:43+13:00

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
One of the challenges in the public sector is getting high level understanding of operational aspects without requiring commercially sensitive data or extensive negotiations to get consistent data from many commericial providers. 

Since the COVID-19 pandemic, policymakers have needed information on ship schedules to better understand trade capacity in and out of New Zealand over time without the specificity of commercial offerings from shipping lines. Enriching a comprehensive data source like AIS (Automatic Identification System) with industry-relevant concepts like voyages and routes (see [blog post](https://shriv-portfolio.netlify.app/post/maritime-data-enrichment/)) allows us to build retrospective ship schedules from a single data source. These schedules, built from movement data, allow comparisons of how ships have actually moved on different routes.

For example, ships that made any Trans-Tasman (`Australia-New Zealand`) voyage in 2021, we see that around a third do the much longer `Latin America-New Zealand-Northern America` routes in between. Only a handful of ships do purely Trans-Tasman voyages for an extended period of time. 

![](shipping-schedules-trans-tasman.png)

A completely different pattern exists for ships that have done a `Australia-New Zealand-Southeastern Asia` route. For these ships, around half run regularly on this route route while another quarter run a variant that only drops Australian ports on the voyage. 

![](shipping-schedules-seasia.png)

#### Disclaimer
The contents and figures in this post are not official outputs from the Ministry of Transport. They are research-oriented exploratory analyses for policymaking. 