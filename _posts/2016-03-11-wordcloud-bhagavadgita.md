---
layout: post
title: WordCloud of Bhagavad Gita
subtitle: "Most frequented words in Hindu&#x27;s holy text"
date: "11-03-2016"
published: true
---


I am not religious. It's not like I believe in atheism too. I like the aspects of teaching about life in the holy books. Therefore,
I thought of checking out the most repeated words in the holy book of Hindus first - _"Bhagavad Gita"_
![wordcloud.png]({{site.baseurl}}/img/wordcloud.png)
The idea came lately after browsing free ebooks on [gutenberg](http://www.gutenberg.org/). That's how I stumble
upon _Bhagavad Gita._ The idea of counting most frequented words strike my mind and that's how I created this beautiful wordcloud of
_Bhagavad Gita._ On the similar path, I want to construct the wordcloud of _Holy Bible_ and _Holy Quran_ as well. But I will do it some other time. 

Here's the wordcloud from Bhagavad Gita's text. The larger the words, the most frequented it is. And they are clustered around
the centre. As the word is moving away from the centre and the size of the word become smaller, it means the word count is getting less
in the text. So the outermost and the smaller words are less in number in the text.

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

Here's the r code which made the above wordcloud
{% highlight r %}
# Load the necessary packages
require(wordcloud)
require(tm)
# Set working directory
setwd("..\\Words Cloud for Bhagavadgita")

# Get the data from the site - www.gutenberg.org where all the texts are available for free
gita <- readLines("http://www.gutenberg.org/cache/epub/2388/pg2388.txt")
# How many lines it read?
length(gita) # 3687 lines
# We need to extract only the lines which is actually the text of Bhagavadgita, and remove other notes
# In order to do that we need to find out from which line it starts and in which line it ends
gita # read all lines to check the start and end lines. 
# It starts from 170 and ends at 3229
gita <- gita[170:3229] # subset rows to get extract the actual text
head(gita) # read the first 6 lines
tail(gita) # read the last 6 lines
# Remove all the punctuations
gita <- gsub(gita, pattern = "[[:punct:]]", replacement = " ")
# Lower case all the text
gita <- tolower(gita)
# It's better to save the text so that we don't have to download the text everytime we run this code
write.csv(gita, "gita.txt", row.names = FALSE)
# Make it corpus so that we create wordcloud
gita_corpus <- Corpus(VectorSource(gita))
gita_corpus <- tm_map(gita_corpus, stripWhitespace) # remove extra spaces in the text
gita_corpus <- tm_map(gita_corpus, removeWords, stopwords()) # remove stopwords
gita_corpus <- tm_map(gita_corpus, removeWords, c("chapter")) # remove the word 'chapter'
gita_corpus <- tm_map(gita_corpus, PlainTextDocument) # convert it into plain text document
# Change it to matrix
gita_DTM <- DocumentTermMatrix(gita_corpus) 
gita_mat <- as.matrix(gita_DTM)
# Count the frequency of the each words in the matrix
gita_word_freq <- sort(colSums(gita_mat), decreasing = TRUE) 
gita_df <- data.frame(word = names(gita_word_freq), freq = gita_word_freq) # change it into data frame
gita_df[1:20, ] # check the first top 20 words
# Generate wordcloud
wordcloud(gita_df$word, gita_df$freq, random.order = FALSE, colors = brewer.pal(6, "Dark2"), max.words = Inf)
{% endhighlight &}
