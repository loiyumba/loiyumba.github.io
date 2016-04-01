---
layout: post
title: Twitter Emotions of Major Indian Airlines
subtitle: Tweets reaction from last week of March 2016
fb-img: https://github.com/loiyumba/loiyumba.github.io/blob/master/img/airline_emotion/airindia.png
---

When I run the process of extracting 500 tweets of '#AirIndia', '#JetAirways', '#Spicejet' and '#IndigoAirlines' each through twitter API, I was able to get for Air India and Jet Airways, but just 165 tweets for Spicejet and only 16 tweets for Indigo Airlines. I wondered what could be the reason that the code is not able to pull 500 tweets for Spicejet and Indigo Airlines. I gave a date range of one month, but it doesn't matter because Twitter allows to retrieve only a week full of tweets. I checked the twitter page on these hashtags and found people didn't tweet for Spicejet and Indigo as many as they tweet for Air India and Jet Airways for that particular week. Also, my general assumption is when we are just happy or satisfied with a service or product, we usually don't share because that is our expectation. We share only when we have extreme feeling about the services or products. So when our expectations are not met, that's when we broadcast to the world and most common medium is Twitter these days. So I imagine more people are upset with Air India and Jet Airways as they get more tweets compare to their counterparts like Spicejet and Indigo Airlines. If we do Google search on ['top airlines in india'](https://www.google.com.sg/search?q=top+airlines+in+india&oq=top+airlin&aqs=chrome.0.69i59j69i57j69i60.2687j0j7&sourceid=chrome&ie=UTF-8), we see the result on the google page itself as Indigo Airlines on top followed by Spicejet. Jet Airways on 3rd spot and so on.

The emotions on the tweets are detected with 'Saif Mohammad's NRC Emotion lexicon' which is included in r package - 'syuzhet'. According to Mohammad, “the NRC emotion lexicon is a list of words and their associations with eight emotions (anger, fear, anticipation, trust, surprise, sadness, joy, and disgust) and two sentiments (negative and positive)”. For more information, see his [page](http://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm)

Here are the tweets reaction on major Indian Airlines from last week of March 2016

[![airindia4]({{ site.url }}/img/airline_emotion/airindia4.png)]({{ site.url }}/img/airline_emotion/airindia4.png)

[![jetairways]({{ site.url }}/img/airline_emotion/jet.png)]({{ site.url }}/img/airline_emotion/jet.png)

[![spicejet]({{ site.url }}/img/airline_emotion/spicejet.png)]({{ site.url }}/img/airline_emotion/spicejet.png)

As we can see from the above 3 plots, the highest percentage of emotions showed on Air India and Jet Airways are fear and sadness whereas Spicejet's highest percentage of emotions are trust and joy.


