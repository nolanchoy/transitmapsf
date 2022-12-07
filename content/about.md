---
title: "About This Site"
coverImage: /images/about-cover.jpg
showDate: false
showTags: false
showPagination: false
showSocial: false
comments: false
---
<!--more-->
## About the Data
Data is pulled from SFMTA's twitter page from Twitter's API every 10 minutes. Tweets are broken down to match on service line, line direction, and interruption location. This information is then mapped to service lines using public data from DataSF.

{{< image classes="fancybox fig-50" src="/images/map-demo1.png" thumbnail="/images/map-demo.png" >}}
{{< image classes="fancybox fig-50" src="/images/map-demo.png" thumbnail="/images/map-demo.png" >}}

## About the Models
3 different models are used to ultimately predict resolution times.