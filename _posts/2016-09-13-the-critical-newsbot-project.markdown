---
layout: post
title:  "The Critical NewsBot Project"
date:   2016-09-13 16:05:04 -0400
categories: newsbot
---
How can we counter the political polarization that stems from algorithmic recommendation of political information online?

I began to think about this question last Spring. I had been studying the ways in which news coverage of disease outbreaks changed based on where the outbreak occurred. The patterns I found worried me and highlighted how different a picture of even these relatively fact-based issues one could get from different news sources. I was also aware of the way in which technology has shaped news consumption through a class I was taking on politics and digital media. 

These threads came together when I first discussed what an online tool to counter political polarization could look like with Janet Vertesi, a sociologist at Princeton. We came up with a simple idea: create a tool that, given an article the user is reading, recommends another article on the same topic but with a different outlook to the user.

In order to implement this, we scraped RSS feeds from various publications and scraped the articles referenced there. Once the headline and text is pulled from the article these are used to determine the topic. The headline and subsequently the text is searched for named entities: names of people, locations, or organizations. The first three named entities in the headline and text are what we take to be the topic and used to query our database of RSS feeds. This is a good conduit for topic in the context of political news because news often centers on names of political figures, organizations, and locations relating to policy or other actions. It has the added benefit of being a lightweight and reproducible technique. The database is then searched for articles where either the title or the description contains the topic words. If none are found, the database is then searched for pairs of words in the topic, and if still none are found it is searched for each word individually.

I noticed that the system would fail in cases where the same topic is discussed in completely different terms on the opposite sides of the political spectrum. If the same issue was identified with different political figures or organizations depending on the slant of the publication, the NewsBot would not be able to identify that the same topic was being discussed because the discourses surrounding political issues can be so distinct depending on political leanings.  

This brings us to the current stage in the development of the project: can we back up and find or develop a topic modelling system that is resistant to the [framing][framing] that political entities engage in? Can we measure this framing through a quantitative analysis?

These are the questions I will seek to answer in moving forward with this project. 

[framing]: http://www.cognitivepolicyworks.com/resource-center/frame-analysis-framing-tutorials/simple-framing/
