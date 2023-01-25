---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Travel Activity Patterns"
summary: ""
authors: []
tags: []
categories: []
date: 2023-01-25T16:07:23+13:00

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
Transport policy that aims to modify travel or activity behaviour must first understand what people do, how, why and with whom. Without it policymakers risk introducing misaligned policies to the desired behaviour change or creating asymmetric distributional impact where some groups are considerably more disadvantaged than others. 

However, understanding the intracies of daily travel and activity behaviour is a high dimensional problem requiring reduction in complexity before it becomes useful for testing policy impacts. 

Clustering is a common approach that both reduces complexity in the data as well as creating additional meaning from the clusters themselves. With the addition of sequence analysis we can preserve temporal information of activity patterns while allowing individual variability to be aggregated as clusters / typologies. The individuals within the clusters can be joined back to the person dataset for distributional impact analyses. 

Almost 6,700 days of daily activities done by ~3000 individuals in one year of data (2017) collected by the Household Travel Survey can be neatly summarised into three daily typologies.

1.  Work commuting
2.  Education
3.  Mainly, home, errands and leisure

![](three-typologies.png)

Generating splits further down the dendrogram can unearth more nuance. For example, Work commuting cluster splits into two additional typologies: 

1. Earlybirds at work with diffused morning and evening commuting times. 
2. Regular 9-5ers with a a strong single morning and evening commute peak at 8 am and 5:30 pm respectively

![](work-cluster-split.png)


#### Disclaimer
The contents and figures in this post are not official outputs from the Ministry of Transport. They are research-oriented exploratory analyses for policymaking. 