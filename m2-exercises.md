_All four exercises are on this page. Don't forget to scroll. If you have difficulties, or if the instructions need clarification, please click the 'issues' button and leave a note. Feel free to fork and improve these instructions, if you are so inclined._

# Background
Where do we go to find data? Part of that problem is solved by knowing what question you are asking, and what _kinds_ of data would help solve that question. Let's assume that you have a pretty good question you want an answer to - say, something concerning social and household history in early Ottawa, like what was the role of 'corner' stores (if such things exist?) in fostering a sense of neighbourhood - and begin thinking about how you'd find data to explore that question. 

[Ian Milligan](http://ianmilligan.ca) recently gave a [workshop on these issues](https://ianmilli.files.wordpress.com/2015/01/downloading-sources2.pdf). He identifies a few different ways by which you might obtain your data, and we will follow him closely as we look at:

+ The Dream Case
+ Scraping Data yourself with free software (Outwit Hub)
+ Application Programming Interfaces (APIs)
+ Wget

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

# Exercise 2: Outwit Hub
Download, and install, [outwit hub](https://www.outwit.com/products/hub/). Do not buy it (not unless you really want to; the free trial is good enough for our purposes here)

Outwit hub is a piece of software that lets you scrape the html of a webpage. It comes with its own browser. In essence, you look at the html source code of your page to identify the *markers* that embrace the information you want. Outwit then copies just that information into a table for you, which you can then download. Take a look at the [Suda Online](http://www.stoa.org/sol/) and do a search for 'pie' (the Suda is a 10th century Byzantine Greek encyclopedia, and its online version is one of the earliest examples of what we'd now recognize as digital humanities scholarship). 

Right-click anywhere on the results page, and 'view source'. You'll see something like this:
![Imgur](http://i.imgur.com/zCSRR9H.png)
The record number - the Adler number - is very clearly marked, as is the translation. Those are the bits we want. So

Open outwit hub. Copy and paste the search URL into the Outwit hub address bar:
![Imgur](http://i.imgur.com/fDM1tog.png)

At the bottom of the page - that's where you tell Outwit how to scrape that source.  Click ‘scrapers,’ then ‘new,’ give it a name. Enter the markers that you are interested in:
![Imgur](http://i.imgur.com/5SdbgeQ.png)

Hit Execute to run the scraper. Press ‘Catch’ to move it into your memory. Press 'export' to generate (and save) a spreadsheet of your data.

Write this exercise up in your notebook. What other data does outwit include with your export? How might that data be useful?

# Exercise 3: APIs
Sometimes, a website will have what is called an 'application programming interface'. In essence, this lets a program on your computer talk to the computer serving the website you're interested in, such that the website gives you the data that you're looking for.

That is, instead of *you* punching in the search terms, and copying and pasting the results, you get the computer to do it. More or less. The thing is, the results come back to you in a machine-readable format - often, JSON, which is a kind of text format. It looks like this:
![Imgur](http://i.imgur.com/LtZWyle.png)

The 'Canadiana Discovery Portal' has tonnes of materials related to Canada's history, from a wide variety of sources. Its search page is at: http://search.canadiana.ca/

+ Go there, and search "ottawa" and set the date range to 1800 to 1900. Hit enter. You are presented with a page of results. But do you notice the address bar of your browser? It'll say something like this:

http://search.canadiana.ca/search?q=ottawa&field=&df=1800&dt=1900

56 249 results! That's a lot of data. Your search query has been put into the URL. You're looking at the API! Everything after /search is a command that you are sending to the Canadiana server.

Scroll through the results, and you'll see a number just before the ?

http://search.canadiana.ca/search/2?df=1800&dt=1900&q=ottawa&field=

http://search.canadiana.ca/search/3?df=1800&dt=1900&q=ottawa&field=

http://search.canadiana.ca/search/4?df=1800&dt=1900&q=ottawa&field=

....all the way up to 5625 (ie, 10 results per page, so 56249 / 10).

 If you go to http://search.canadiana.ca/support/api you can see the full list of options. What we are particularly interested in now is the bit that looks like this:

&fmt=json

Add that to your query URL. How different the results now look! What's nice here is that the data is formatted in a way that makes sense to a machine - which we'll learn more about in due course.

If you look back at the full list of API options, you'll see at the bottom that one of the options is 'retrieving individual item records'; the key for that is a field called 'oocihm'. If you look at your page of json results, and scroll through them, you'll see that each individual record has its own oocihm number. If we could get a list of those, we'd be able to programmatically slot them into the commands for retrieving individual item records:

http://eco.canadiana.ca/view/oocihm.16278/?r=0&s=1&fmt=json&api_text=1

The problem is: how to retrieve those oocihm numbers. The answer is, 'we write a program'. And the program that you want can be [found here](http://ianmilligan.ca/api-example-sh/). Study that program carefully. There are a number of useful things happening in there, notably 'curl', 'jq', 'sed', 'awk'. curl  is a program for downloading webpages, jq for dealing with json, and sed and awk for searching within and cleaning up text. If this all sounds greek to you, there is an excellent gentle introduction over at [William Turkel's blog](http://williamjturkel.net/2013/06/15/basic-text-analysis-with-command-line-tools-in-linux/).

### Mac instructions:

If you have a Mac, copy and paste that program into Textwrangler or a similar program; save it to your desktop as 'canadiana.sh'. Open your terminal program (which you can find under 'applications' and then 'utilities'.) Navigate to your desktop:

`cd desktop`

then tell your computer that this 'canadiana.sh' program is one that you want to run:

`sudo chmod 700 file.sh`

And then you can run it by typing:

`./canadiana.sh`  but *don't* do that yet! You'll need to change the search parameters to reflect your own interests. Do you see how you can do that? Do that, then run the command. Move your results into a sensible location on your computer. Make a new entry (or entries) into your research notebook about this process, what worked, what hasn't, what you've found, where things are, and so on. You might want to upload your script (your .sh file) to your repository. Remember: the goal is so that you can come back to all this in a month's time and figure out _exactly what you did_ to collect your data. 

### Windows instructions:
1. You'll need gitbash
2. You'll need jq
3. You'll need CoreUtils

Install these. Restart your computer. 

Or maybe cygwin. I'm installing it right now, will get back to you.

_more to come_

# Wget

Finally, wget. This is an extremely useful piece of software. First thing: you'll need to install it. As ever, this is simple on a Mac and a bit more difficult on a PC. Go to [the programming historian tutorial on wget](http://programminghistorian.org/lessons/automated-downloading-with-wget) and get it installed.

This section will follow [Milligan p52-64](https://ianmilli.files.wordpress.com/2015/01/downloading-sources2.pdf).
