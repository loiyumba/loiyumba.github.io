---
layout: post
title: WordCloud of Bhagavad Gita
subtitle: "Most frequented words in Hindu&#x27;s holy text"
date: "11-03-2016"
published: true
fb-img: http://loiyumba.github.io/img/wordcloud.png
---


The aspects of teaching about life in the holy books are humongous. Therefore, I thought of checking out the most repeated words in the holy book of Hindus first - _"Bhagavad Gita"_

The idea came lately after browsing free ebooks on [gutenberg](http://www.gutenberg.org/). The idea of counting most frequented words in any of the texts available online strike my mind, and that's how I created this beautiful wordcloud of _Bhagavad Gita._ I could have done with any of the texts but a hard copy of _Bhagavad Gita_ is lying on my desk. So it's obvious that I start with this holy book first. On the similar path, I want to construct the wordcloud of _Holy Bible_ and _Holy Quran_ as well. I will do it some other time. 

Here's the wordcloud from Bhagavad Gita's text. The larger the words, the most frequented it is. And they are clustered around
the centre. As the word is moving away from the centre and the size of the word become smaller, it means the word count is getting less in the text. So the outermost and the smaller words are less in number in the text.
[![wordcloud]({{ site.url }}/img/wordcloud.png)]({{ site.url }}/img/wordcloud.png)

So the words like thou, one, soul, thy, thee, prince, life, arjuna, heart, self, krishna, lord, shall, etc. are the most frequented words
in this holy text. Below is the actual count of the words and I just displayed the highest top 20 in the text. 

| Words        | Count          |
| ------------- |:-------------:|
| thou     | 134 |
| one      | 96      |
| soul | 93      |
| thy | 93 |
| thee | 90 |
| life | 74 |
| prince | 62 |
| shall | 59 |
| heart | 57 |
| self | 56 |
| will | 54 |
| arjuna | 52 |
| hath | 52 |
| know | 52 |
| lord | 52 |
| man | 52 | 
| krishna | 49 |
| yet | 45 |
| mind | 44 |
| men | 43 |

Here's the r code for generating the above wordcloud  
```r
x <- function(x){
if(x < 5){
y <- x + 10
} else {
y <- 0
```

