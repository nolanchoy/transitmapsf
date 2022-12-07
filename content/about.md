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
Data is pulled from SFMTA's twitter page from Twitter's API every 10 minutes. Tweets are broken down to match on service line, line direction, and interruption location. This information is then mapped to service lines using public transit line data from SF Gov's Open Data.

{{< image classes="fancybox fig-50" src="/images/map-demo1.png" thumbnail="/images/map-demo1.png" >}}
{{< image classes="fancybox fig-50 clear" src="/images/map-demo.png" thumbnail="/images/map-demo.png" >}}

## About the Models
Three different models are incorporated to ultimately predict resolution times. A **Named Entity Recognition** (NER) model is used to extract incidents from tweet text. A **Support Vector Machine** (SVM) classifier is used to place the extracted event into pre-defined classes. Finally, a **prediction** model is used to predict the estimated service interruption resolution time.