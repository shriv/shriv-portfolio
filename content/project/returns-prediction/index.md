---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Predicting customer behaviour: returns"
summary: ""
authors: []
tags: []
categories: []
date: 2020-11-30T21:23:41+13:00

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

Returns are an inevitable consequence of spatial and temporal separation of purchase from physical interation with the item. Despite advanced multimedia in presenting item characteristics to the customer, there is still a fundamental lack of tactile understanding. The importance of such an understanding is both a function of customer preference and item characteristics. The physical feel and wear of some items are inherently harder to communicate and, customers' themselves have different preferences of what they expect from the photos and videos. As a result, returns are usually distributed. The shape and extremes of returns are, of course, variable depending on the item type and the brand / retailer! 

The level of variability in returns prompts a desire to understand _why_ returns happen in the first place. For garments at a particular retailer, I built two simple returns models to disseminate how items and customer characteristics contribute to when returns happen. The model (left figure) with item characteristics alone showed that returns are more unpredictable than expected. Including features based on customer behaviours (right figure) lift prediction accuracy considerably. 

Working on such an intersting domain problem highlighted the importance of complext interactions and intenstions. For example, any outcome of behaviour requires not only a sense of the customer's intent when shopping but also their interaction and attitudes towards the browsed items. Had the project continued for longer, the creation of customer preferences, intentions and interactions would have been the next step in building a better model. 

![](prediction-performance.png)


