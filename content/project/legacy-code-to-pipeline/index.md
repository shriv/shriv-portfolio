---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "From Legacy Code to Pipeline"
summary: ""
authors: []
tags: []
categories: []
date: 2021-01-25T20:49:56+13:00

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

Legacy code is a burden for any developer. Depending on the state of the code, maintenance and improvements are not necessarily simple. From my experience in the public sector, legacy code for analyses and ETL (Extract, Transform, Load) are neither written by developers who were conversant in modern software development practices (like version control, automation, unit testing etc.) nor is the code particularly well-documented. As a result, maintenance is time consuming, manual and unwieldy. As part of my recent role in the government, inherited code bases became a nightmare to maintain and use until I discovered the delightful trifecta of `jupyter`, `saspy` and `exchangelib`. 

`jupyter`: creates a trivial single click "pipeline" of steps that can be documented and explained at a high level
`saspy`: allows python to send SAS code to the installed SAS program 
`exchangelib`: allows python to access Outlook mailboxes through the Exchange Web Services API for querying emails, download attachments etc. 

