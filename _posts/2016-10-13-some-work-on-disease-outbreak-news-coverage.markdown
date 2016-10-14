---
layout: post
title:  "Some Work On Disease Outbreak News Coverage"
date:   2016-10-13 16:05:04 -0400
categories: language, policy
---

The way in which disease outbreaks are covered in newspapers has concrete impact on public health responses and general public preparedness for health events. Last year, I assembled a large dataset of news reports through web scraping and use automated text analysis techniques to uncover patterns in this coverage. Because I'm doing some more work in this space recently, I wanted to go over this work as a way to reflect on it.

The ultimate object of the study was to gain some insight into the way newspapers report on disease outbreaks in order to understand how this might influence public opinion. With this in mind, it was important to select news sources that influence public opinion most. The most obvious way to do this is to select the sources that are most read. However, even doing this is easier said than done: how should online readership be weighted as compared with print readership? Should I use the most recent figures on readership or take an average over the period of study? 

I settled on the below publications*:
Africa: the Independent Online
Asia: The Asahi Shimbun
Europe: BBC
North America: New York Times
Oceania: Sydney Morning Herald

Now on to results…

I analyzed the overall degree to which the number of cases in a disease outbreak bears on the amount of news coverage of the outbreak. None of the correlational coefficients are highly positive, and some are even slightly negative, indicating that there is indeed no connection between the number of cases of a disease outbreak and the amount of coverage of the outbreak as measured by the number of articles each publication publishes on the outbreak. Similarly, I find no connection between the number of deaths associated with an outbreak and the amount of coverage the outbreak receives.

![My helpful screenshot](http://daphneweinstein.github.io/assets/p3_img1)


Next I examine the way in which sentiment polarity is influenced by the number of cases in a disease outbreak. As we can see below, the data appear quite random. The correlational coefficient is small for all of the publications examined.

![My helpful screenshot](http://daphneweinstein.github.io/assets/p3_img2)



While we have seen that the size of an outbreak does not determine its degree of coverage, one factor that does seem to affect the amount of coverage an outbreak receives, when combined with the number of cases of the outbreak is the continent on which the outbreak occurred. I first examine how many articles are published in each publication compared to the number of outbreaks on each continent. The results are displayed below.

![My helpful screenshot](http://daphneweinstein.github.io/assets/p3_img3)


These results evidence the overwhelming amount of recent coverage of the Zika virus. Next I look at the amount of coverage of a disease compared to the incidence of the disease. Here we see that how widespread a disease is is differentially factored into coverage depending on the location of an outbreak. The differential is so large between Europe and North America and other

![My helpful screenshot](http://daphneweinstein.github.io/assets/p3_img4)


continents I examine as to overwhelm the other data. I display it separately below. Coverage of outbreaks compared to their incidence on the African continent is lowest overall, while coverage of South and Central American and Asian outbreaks is somewhat larger. To give one a sense of what this means, for every single case of a disease outbreak in Europe the BBC publishes on average 14.83 articles; but for every case in Africa it would publish an average of .0021 article. 
![My helpful screenshot](http://daphneweinstein.github.io/assets/p3_img5)


This large discrepancy in coverage when compared with death rate could be attributable to the inferior containment and control of disease outbreaks on the African continent due to a lack of structural resources, among various interwoven factors. 

Informed by the patterns I found above in a continent-differentiated analysis, I preliminarily examine word use in the BBC on a continent-by-continent basis. I list some potentially interesting differences in the frequency of word appearance below. This is in the form of a ranking of word stems used in BBC news articles on outbreaks by continent (i.e. concern- was the 368th most common word stem to be used among all articles about outbreaks in Africa between 2006 and 2015). This data is preliminary but serves to demonstrate the way in which patterns might emerge with a more complete analysis.

![](http://daphneweinstein.github.io/assets/p3_img6)


My research showed that there is no overall correlation between case rate or death rate and coverage. I also found a lower rate of coverage for cases in outbreaks outside of Europe and North America. 

-----------------------------------------------------------------------------------

* Many media scholars question the importance of actual readers of news. News diffuses through the direct pathway of news consumption, and through discussion with those surrounding. This second pathway is especially relevant in poorer areas with less ready access to news. However, the ways in which news coverage transmitted secondhand influence opinion are no less important to my study. With this in mind, I selected one news source from each of Africa, Asia, Europe, North America, and Oceania. I exclude other continents due to the lack of significant amounts of English language reporting. 

Because print news circulation is low on the African continent as a whole I chose the source with the highest online readership on the continent: the Independent Online.

I chose Japan’s Asahi Shimbun as the Asian news source as it is the second widest circulated newspaper in the world (second to another Japanese newspaper with no English edition). It thus surpassed any English news source in terms of print circulation. Because many of the most widely circulated print sources of news are located on the Asian continent, I rely on print media circulation as the main determiner of my choice, as the fact that print news is so widely circulated makes it a good conduit for people’s information consumption on the whole. 

Of the most popular English-language news sources in terms of both print and online readership in Europe, most are tabloids. Because of this and the large audience for the British Broadcasting Corporation (BBC) across both radio and online news, I chose the BBC as the news source for Europe.

I chose The New York Times as the representative news source for North America. It has the second largest online readership in the world combined with the third largest print circulation in the US. I prioritize digital circulation as it is increasingly the more important mode of communication, and because the Times’ lead in this area is so dramatic. 

In the case of Oceania, I choose The Sydney Morning Herald (Sydney Herald) as the index news source for similar reasons to my choice of the Times. It has the largest online readership in Oceania combined with the fourth largest print readership in Australia.

As is obvious all of these choices required me to judge the value of one metric of popularity over the other based on contextual clues. These choices are not decisive but they give a general sense of widely consumed news in their respective locales. Of course, the level of granularity is also extremely low and representativeness likely varies based on continent. It is likely that a large portion of the US population (which comprises a majority of North Americans) reads or knows someone who reads The New York Times while it is unlikely that the same is true of any given newspaper in the Asian continent.
