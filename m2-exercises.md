_All four exercises are on this page. Don't forget to scroll. If you have difficulties, or if the instructions need clarification, please click the 'issues' button and leave a note. Feel free to fork and improve these instructions, if you are so inclined._

# Background
Where do we go to find data? Part of that problem is solved by knowing what question you are asking, and what _kinds_ of data would help solve that question. Let's assume that you have a pretty good question you want an answer to - say, something concerning social and household history in early Ottawa, like what was the role of 'corner' stores (if such things exist?) in fostering a sense of neighbourhood - and begin thinking about how you'd find data to explore that question. 

[Ian Milligan](http://ianmilligan.ca) recently gave a [workshop on these issues](https://ianmilli.files.wordpress.com/2015/01/downloading-sources2.pdf). He identifies a few different ways by which you might obtain your data:

+ The Dream Case
+ Application Programming Interfaces (APIs)
+ Scraping Data yourself (Outwit Hub)
+ Computational Methods (Python, Bash, [Programming Historian](http://theprogramminghistorian.ca) 

There is so much data available; with these methods, we can gather enormous amounts that will let us see large-scale macroscopic patterns. At the same time, it allows us to dive into the details with comparative ease. The thing is, not all digital data are created equally. Google has spent millions digitizing *everything*; newspapers have digitized their own collections. Genealogists and local historical societies upload yoinks of digitized photographs, wills, local tax records, [you-name-it](http://www.bytown.net/), *every day*. But, consider what Milligan has to say about ['illusionary order'](http://ianmilligan.ca/2012/03/26/illusionary-order-cautionary-notes-for-online-newspapers/):

> [...] poor and misunderstood use of online newspapers can skew historical research. In a conference presentation or a lecture, it’s not uknown to see the familiar yellow highlighting of found searchwords on projected images: indicative of how the original primary material was obtained. But this historical approach generally usually remains unspoken, without a critical methodological reflection. As I hope I’ll show here, using Pages of the Past uncritically for historical research is akin to using a volume of the Canadian Historical Review with 10% or so of the pages ripped out. Historians, journalists, policy researchers, genealogists, and amateur researchers need to at least have a basic understanding of what goes on behind the black box.

Please go and read that full article. You should makes some notes: what are some of the key dangers? Reflect: how have you used digitized resources uncritically in the past?
---------

Remember: 'To digitize' doesn't - or shouldn't - mean uploading a photograph of a document. There's a lot more going on that that. We'll get to that in a moment.

# Exercise 1: The Dream Case
In the dream case, your data are not just images, but are actually sorted and structured into some kind of pre-existing database. There are choices made in the *creation* of the database, but a good database, a good project, will lay out for you their decision making, their corpora, and how they've dealt with ambiguity and so on. You search using a robust interface, and you get a well-formed spreadsheet of data in return. Two examples of 'dream case' data:

+ [Epigraphic Database Heidelberg](http://edh-www.adw.uni-heidelberg.de/inschrift/suche)
+ [Commwealth War Graves Commission, Find War Dead](http://www.cwgc.org/find-war-dead.aspx)

Explore both databases. Perform a search of interest to you. In the case of the epigraphic database, if you've done any Latin, try searching for terms related to occupations; or you could search '[Figlin*](http://www.latin-dictionary.org/Latin-English-Dictionary/figlina)'. In the CWGC database, search your own surname. Download your results. You now have data that you can explore! In your online research notebook, make a record (or records) of what you searched, the URL for your search & its results, and where you're keeping your data. 

# Exercise 2: APIs
Sometimes, a website will have what is called an 'application programming interface'. In essence, this lets a program on your computer talk to the computer serving the website you're interested in, such that the website gives you the data that you're looking for.

That is, instead of *you* punching in the search terms, and copying and pasting the results, you get the computer to do it. More or less. The thing is, the results come back to you in a machine-readable format - often, JSON, which is a kind of text format. It looks like this:
![Imgur](http://i.imgur.com/LtZWyle.png)

The 'Canadiana Discovery Portal' has tonnes of materials related to Canada's history, from a wide variety of sources.
http://search.canadiana.ca/

XERCISE: principles of search; digital history treasure hunt
EXERCISE: semantic data, xml, and TEI tutorials
EXERCISE: text versus other kinds of digital data: how to digitize 3d objects as a lesson in metadata
EXERCISE: grabbing data using

he exercises in this module will teach you how to use wget on the command line to grab webpages; they will introduce you to the concept of APIs and what you might achieve with them as a historian; they will have you use some existing free and commercial tools for webscraping; and we will also learn how to grab social media data as well.
