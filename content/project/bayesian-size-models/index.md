---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Learning customer preference: from size to fit"
summary: ""
authors: []
tags: []
categories: []
date: 2020-12-01T20:20:38+13:00

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

The conundrum of size vs. fit continues to plague online shoppers and in turn, retailers. The iteration of purchase, retention / return and re-purchse is an opportunity for retailers to learn customer preferences and offer better purchasing advice for future customers. With only transaction and browsing behaviour data, recommendations are a popular offering. However, if retailers can use customer shape data directly, obtained through online fit tools, they can evolve their understanding of size as fit as a pathway for better customer advice. 

In this project, I chose to remodel the size chart as a  "fit chart". A fit chart begins as a size chart - one that is usually designed by the product team at the retailer / brand. Once the garment is on the site and has associated purchases or returns, the size chart can be re-calculated as a fit chart through a suitable statistical model. 

Given the typical distributions of population parameters, I began with a bayesian model that modelled each fit point (bust, waist and hips)  with a simple normal distribution. While the model performance is highly dependent on the retailer and customer behaviour combinations, I found that some retailer models could attain [AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve) values of 0.78 through this simple shift in perspective from _size_ to _fit_. Aside from its simplicity, the bayesian model is also able to handle the large discrepancy in sales between 'popular' and 'select' items and able to offer useful outputs with both low and large volumes of sales data. 

![](auc-base.png)

Extending the simple normal model to including priors was able to significantly improve the fit charts. While the choice of a suitable prior was challenging I found that the impact of a good prior resulted in tidier outputs from the model. Even a prior that is an average across all the data can make a difference. For example, the dispersion and widths of the distributions can be reduced significantly. 

![](priors-effect.png)


_Featured image Yoda by Ben Davis from the Noun Project_