---
title:  "Hong Kong Lennon Wall Map"
last_modified_at: 2019-07-25T04:04:00+08:00
---
Visualization of the Hong Kong Lennon Wall Instagram Posts in a Map

[Web App](https://cameronlai.github.io/hk-lennon-wall)

[Source code](https://github.com/cameronlai/hk-lennon-wall)

June 2019 marks an important point of history for Hong Kong. Multiple large scale protests took place against the extradition bill, including the ones which 1 million and 2 million people went on the streets on [9th June, 2019](https://www.bbc.com/news/world-asia-china-48572130) and [16th June, 2019](https://www.bbc.com/news/world-asia-china-48656471).

In response to all the protest and violence, many thousands of people posted colourful post-it notes in Hong Kong to express democratic wishes and political views. This took place in 2014 during the ["Umbrella Protest"](https://en.wikipedia.org/wiki/2014_Hong_Kong_protests) at Admiralty. For the 2019 protests, the "Lennon Wall" went viral and is now in multiple locations (>100) in Hong Kong. This term ["Lennon Wall"](https://en.wikipedia.org/wiki/Lennon_Wall) originated from Prague, Czech republic, where a normal has been filled with John Lennon-inspired graffiti since 1980 shortly after John Lennon was murdered. It symbolizes freedom of speech, which everyone can express the views on the wall, no matter which political stance they take.

This project aims to show the distribution of the "Lennon Wall" activity across Hong Kong during the important times. It started by crawling the hashtag [#連儂牆](https://www.instagram.com/explore/tags/%E9%80%A3%E5%84%82%E7%89%86/). The metadata from Instagram was used to build a JSON file for the website. A total of 729 posts were collected, clustered into 80 markers on the map with k-means algorithm under the UTM coordinate system. The website is built with Vue.js, utilizing the the Vue2Leaflet library. 

The amount of Lennon Walls and post-it notes in Hong Kong is spectacular. It not only serves as a place where people express views and discuss political topics, it shows the strength of Hong Kong people's voice. Not only are we protesting against the extradition bill, we are also exploring how Hong Kong and China's relationship should evolve under the "One Country, Two System" model. Wish the Hong Kong government can listen to Hong Kong people's opinion and make Hong Kong great together again!