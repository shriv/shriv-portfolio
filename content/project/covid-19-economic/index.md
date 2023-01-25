---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "COVID-19 impacts on economic indicators"
summary: ""
authors: []
tags: []
categories: []
date: 2023-01-25T21:23:25+13:00

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
The COVID-19 pandemic has affected economic activity around the world. However, direct impacts cannot be calculated with a comparison between the last pre-pandemic year and current pandemic years. For indicators that respond quickly to singular, large shocks like a global pandemic, one approach for extracting a causal impact is to subtract the actual values from a projected counterfactual generated from trends prior to the shock. 

![](counterfactuals.png)

Easily available economic indicators of container trade, in terms of TEU (twenty foot equivalent units), are used to estimate the causal impact of the global pandemic that started in 2020 since *"..the dynamics of the breakbulk market are related to manufacturing and consumption."* ([Geography of Transport Systems Ch. 5.4.2](https://transportgeography.org/contents/chapter5/maritime-transportation/#2_Maritime_Traffic)) Imports are connected to consumption (demand) while exports link to manufacturing (supply as a response to external demand). 

For container imports, the counterfactual predictions from an [ETS](https://otexts.com/fpp3/expsmooth.html) (exponential smoothing) model show that most of 2020 volumes were considerably below expected. From 2021, the predictions and the actuals fall in a little closer together possibly indicating some recovery. 

![](import-impacts.png)

Overall exports show no clear trend since New Zealand exports primary products - each with different seasonalities and trends. Instead, exports need to be modelled separately by commodity. Wood products show the greatest reductions and ongoing dampening while food commodities have seen little change to expectations. 

![](export-impacts.png)


#### Disclaimer
The contents and figures in this post are not official outputs from the Ministry of Transport. They are research-oriented exploratory analyses intended as demonstrations of approaches and techniques relevant to public sector data science. 