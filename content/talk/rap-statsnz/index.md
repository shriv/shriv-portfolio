---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "RAPping in the public sector"
event: "Statistics NZ seminar"
event_url:
location:
address:
  street:
  city:
  region:
  postcode:
  country:
summary:
abstract: "Straggling legacy scripts (often SAS) requiring manual steps are a common 'feature' of data analysis in the public sector. However, refactoring such scripts to modern, reproducible analytical pipelines (RAP) can be challenging due to a lack of IT infrastructure or high complexity. In such situations, interim solutions can at least reduce manual effort and mental overhead.

The first part of the talk will present one type of 'interim' solution: using Python as a glue to create one-click execution pipelines. Manual tasks like downloading data from email, updating new data file names in scripts, running scripts in sequence etc. can be managed with Python and its rich ecosystem of packages. In this talk, I will showcase how three Python packages: `exchangelib`, `jupyter` and `saspy` - can create quick and easy automated versions of legacy SAS code that contain many types of manual steps.

The second part of the talk will briefly describe how the interim solution can be upgraded for longer term use with docker, pipeline orchestration tools and, writing tidy "online" documentation."

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: 2021-07-27
date_end: 
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: 2021-08-07T14:43:00+12:00

authors: []
tags: []

# Is this a featured talk? (true/false)
featured: false

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

# Optional filename of your slides within your talk's folder or a URL.
url_slides:

url_code:
url_pdf: https://github.com/shriv/statsnz-rap/blob/master/RAPping%20in%20the%20public%20sector.pdf
url_video:

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
