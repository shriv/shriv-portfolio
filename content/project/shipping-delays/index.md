---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Voyage distributions and shipping Delays"
summary: ""
authors: []
tags: []
categories: []
date: 2023-01-24T09:15:28+13:00

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

The movement of ships and depdendence on international ports has been left alone as a market optimisation by New Zealand policymakers. That is, the competitive market will converge on optimisied routes given maritime network structure, demand and port capacity / attractiveness. However, the cascading set of labourforce disruptions and stringent COVID-19 policies have resulted in significant delays and disruptions to ship schedules. 

With port visits extracted from AIS (Automatic Identification System)m GPS-like data of ship movements, we can look beyond the territorial waters of the country to get the full international voyage component of ships that visit New Zealand. 

Given New Zealand's geographical position as well as its wide set of trading partners, we see considerable variation in both the absolute value as well as the shape. Longer routes like `Australia-Eastern Asia-New Zealand` and `Latin America-New Zealand-Northern America` have the most stable shape (symmetric Gaussian/Lorentzian) while voyages on the considerably closer Trans-Tasman route (`Australia-New Zealand`) are heavily skewed. A long tail is also seen for voyages on the important `Australia-New Zealand-Southeastern Asia` route, connecting New Zealand to key trans-shipment hubs like Singapore and Port Klang. 

![](voyage-distributions.png)

We can zoom into the temporal patterns for voyages in the two problematic routes. Both display different reasons for issues. For Trans-Tasman voyages, delays have no clear pattern. For voyages to Southeastern Asia, voyage durations peaked between April - June 2021 before decreasing again.

![](voyage-time-series.png)

#### Disclaimer
The contents and figures in this post are not official outputs from the Ministry of Transport. They are research-oriented exploratory analyses for policymaking. 