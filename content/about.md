---
title: "About This Site"
coverImage: /images/about-cover.jpg
showDate: false
showTags: false
showPagination: false
showSocial: false
comments: false
---
{{< alert warning>}}
Servers may undergo occasional maintenance.
{{< /alert >}}
{{< alert info>}}
To view specific lines, use the layers menu in the top-right of the map. Deselect "Show All" then select your line.
* **Green** lines indicate working service. 
* **Orange** lines indicate recently resolved service interruptions. 
* **Red** lines indicate ongoing service interruptions.
{{< /alert >}}

## About the site
"Is my Muni delayed?" "Where?" "When will it be back up?" 

This site was created by Nolan Choy to track and visualize transit service disruptions in San Francisco and to offer best estimates for service resumption times. You can get in touch with me at transitmapsf@gmail.com.

## About the data
Data is pulled from SFMTA's twitter feed via Twitter's API every 10 minutes. Raw data, in the form of natural language text, is analyzed for service line, line direction, and interruption location. This information is then visualized on a map using public transit line data from SF Gov's Open Data.

{{< image classes="fancybox fig-50" src="/images/map-demo1.png" thumbnail="/images/map-demo1.png" >}}
{{< image classes="fancybox fig-50 clear" src="/images/map-demo.png" thumbnail="/images/map-demo.png" >}}

## About the models
Three different models are incorporated to ultimately predict resolution times. A **Named Entity Recognition** (NER) model is used to extract incidents from tweet text. A **Support Vector Machine** (SVM) classifier is used to place the extracted event into pre-defined classes. Finally, a **prediction** model is used to predict the estimated service interruption resolution time.

## Data Considerations
To highlight some challenges with SFMTA tweet data:
* Origin tweets are an engineered feature due to the API only reporting the retweet ID and not the root tweet ID
  * SFMTA tweets are essentially tweet chains so tracking the original tweet is important as it typically provides all the information for affected lines
* ATTN tweets can sometimes be an update and are not always the root tweet
* Sometimes an event can be a standalone ATTN tweet without a final update
* Tweets that indicate lines without incidents (e.g. "49 is unaffected") would be identified as an affected line. I have not incorporated sentiment analysis into this
* SFMTA tweets are managed by a human operator and terminology is not always standardized
  * e.g. The Powell-Hyde Cable Car line has been called "Powell-Hyde", "Powell / Hyde" and "Powell Hyde".
  * Different abbreviations for street names is annoying. e.g "Sac." instead of "Sacramento"
  * Different abbreviations in general. e.g. "b/t", "btwn", and "between"