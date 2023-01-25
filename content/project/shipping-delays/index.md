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

Container shipping has been left to the market by New Zealand policymakers - expecting competitive market forces to converge on optimal routes given maritime network structure, demand and port capacity / attractiveness. However, a cascading set of labourforce disruptions and stringent COVID-19 policies have resulted in significant delays to container ship voyages since the onset of the COVID-19 pandemic. 

Given New Zealand's geographical position as well as its wide set of trading partners, we see considerable variation in both the absolute value as well as the shape of voyage durations. Longer routes like `Australia-Eastern Asia-New Zealand` and `Latin America-New Zealand-Northern America` have the most stable shape (symmetric Gaussian/Lorentzian) while voyages on the considerably closer Trans-Tasman route (`Australia-New Zealand`) are heavily skewed. A long tail is also seen for voyages on the important `Australia-New Zealand-Southeastern Asia` route - connecting New Zealand to key trans-shipment hubs like Singapore and Port Klang. 

![](voyage-distributions.png)

We can zoom into the temporal patterns for voyages on the two problematic routes. For Trans-Tasman voyages, delays have no clear pattern. For voyages to Southeastern Asia, voyage durations peaked between April - June 2021 before decreasing again.

![](voyage-time-series.png)

#### Disclaimer
The contents and figures in this post are not official outputs from the Ministry of Transport. They are research-oriented exploratory analyses intended as demonstrations of approaches and techniques relevant to public sector data science. 