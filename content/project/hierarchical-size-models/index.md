---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Modelling the real world with hierarchical models"
summary: ""
authors: []
tags: []
categories: []
date: 2020-12-07T10:42:49+13:00

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
A simple model usually assumes no grouping or structure in the data. However, real world processes often have clear hierarchy and structure. For example, Brand A shirts will be more similar to Brand B shirts than Brand A trousers. Thus, a natural extension to modelling fit is to incorporate a hierarchical structure allows that modelling of categories that closely emulate reality, e.g. garment type, fit type (slim, regular, plus) or brand. For example, a single model for all size charts that sell shirts and individual models for each brand. 

![](single-level-hierarchy.png)

More than one level in the model hierarchy requires a re-structuring of the model as a 'multilevel' structure - where all the levels are a _shift_ from a mean value. A forest plot visualisation of fit coefficients can offer both quantitative and domain insight. In _fit_ terms the plot can be interpreted as knitwear having more tolerance and generally accomodating more shapes while shorts and coats fit _smaller_ than the average across all garments. 

![](outfit-centered.png)