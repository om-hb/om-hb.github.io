---
title: "Anniversary Heatmaps"
layout: single
categories:
  - Projects
  - I made Something
tags:
  - Heatmap
  - Presents
  - Gifts
  - Folium
  - Leaflet
  - Data Visualization
  - Google Takeout
  - Python
#date: 2021-07-07 10:00 -0500
#last_modified_at: 2018-02-19T08:06:00-05:00
excerpt: "How I turned my Google Location History into a beautiful Anniversary Gift."
#tagline:
header:
  overlay_image: assets/images/2021-11-09-heatmaps-overview/banner.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
  caption: "Credit: [**mockups-design.com**](https://mockups-design.com/free-poster-frame-mockup-2/)"
  teaser: assets/images/2021-11-09-heatmaps-overview/banner_th.jpg
  # actions:
  #   - label: "More Info"
  #     url: "https://unsplash.com"
#classes: wide
toc: true
toc_label: "Contents"
#toc_icon: "cog"
toc_sticky: true
---

# Background: Getting Data from Google 

Most people today will probably be aware that Google, like many other tech giants, collects large amounts of data about its users. However, what many people probably don't know, is that Google allows its users to download all the data associated to their accounts as an archive file. This can be done using Google's [Takeout Service](https://takeout.google.com/).

Quite some time ago, when the local anti-corona measures were strictest and there wasn't much else to do, I requested my full data to search for potentially interesting insights about myself, hidden between the millions of data points stored about me.[^1]

For the little project that will be described in this post, one file in the exported archive will be of particular interest: *LocationHistory.json*. As the file name already suggests, this file contains most of the information Google has about where I (or more accurately my phone) have been in the past years. And let me tell you: It's *a lot* of information. 1.963.756 geo-positions, to be precise.[^2]

# Turning the Data into a Gift

## The Idea

At the same time I rummaged through my exported data, I was on the lookout for a nice, personal anniversary gift for my girlfriend. At some point it dawned on me, that these two undertakings could probably be combined nicely.

After some brainstorming I settled on the idea of creating visualizations of our first dates, combine them into a collage and to frame them. For the visualization I decided to use heatmaps. 

## The Execution

To create the heatmaps I used Python. For easier handling, I first loaded the *LocationHistory.json* file into a [pandas](https://github.com/pandas-dev/pandas) dataframe. I then wrote a little [folium](https://github.com/python-visualization/folium)-based script, which takes the dataframe, a user specified time frame and some design parameters as inputs and outputs an interactive heatmap of the geo-positions collected in that timeframe. This output looks something like this[^3]:

<iframe src="/assets/html/2021-11-09-heatmaps-overview/heatmap.html" height="450px" width="100%" style="border:none;"></iframe>

After some fine-tuning on the map design - most notably switching to [Stamen Toner](http://maps.stamen.com/#toner/) map tiles - I exported the maps of our first three dates as images. Using a graphics editor, these were then combined into a final collage, which was subsequently printed and framed. The end result looked something like this: 

![A mockup of the final framed poster.](/assets/images/2021-11-09-heatmaps-overview/banner.jpg "A mockup of the final framed poster.")

# The Code

I haven't made the code publicly available yet, as it is a bit messy and not well documented. However, if I can find the time, I will tidy it up a bit, make it available via GitHub and write another short post to explain it in more detail. :relieved:

___

[^1]: More on this endeavor maybe later, in a separate post.
[^2]: Which is not really surprising to me as I'm an active user of Google Maps's [Timeline](https://timeline.google.com/) feature and have [Location History](https://support.google.com/accounts/answer/3118687?hl=en) turned on for years. 
[^3]: Thanks to Rob Williams for providing [this nice guide](https://jayrobwilliams.com/posts/2020/09/jekyll-html) on how to make Leaflet maps work with Jekyll.