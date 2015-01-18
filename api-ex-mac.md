#! /bin/bash
 
# this requires JQ - you can install this by using HOMEBREW
# to install homebrew, visit http://brew.sh OR read this: http://programminghistorian.org/lessons/automated-downloading-with-wget
# to install jq, type 'brew install jq'
# by Steve Marti, by way of Ian Milligan http://ianmilligan.ca/api-example-sh/
# if you need wget, brew install wget
 
pages=$(curl 'http://eco.canadiana.ca/search?q=montenegr*&field=&so=score&df=1914&dt=1918&fmt=json' | jq '.pages')
 
# this goes into the results and reads the value of 'pages' in each one of them.
# it then tells us how many pages we're going to have.
 
echo "Pages:"$pages
 
# this says 'for each one of these pages, download the 'key' value on each page'
 
for i in $(seq 1 $pages)
do
        curl 'http://eco.canadiana.ca/search/'${i}'?q=montenegr*&field=&so=score&df=1914&dt=1918&fmt=json' | jq '.docs[] | {key}' >> results.txt
done
 
# the next two lines take the results.txt file that is quite messy and clean it up. I'll try to explain what they all mean. Basically, tr deletes a given character - so we delete quotation marks "\"" (the slash tells the computer not to treat the quotation mark as a computer code, but as a quotation mark itself), to erase spaces, and to find the phrase "key:" and delete it too.
 
sed -e 's/\"key\": \"//g' results.txt | tr -d "\"" | tr -d "{" | tr -d "}" | tr -s " " | sed '/^\s*$/d' | tr -d ' ' > cleanlist.txt
# this adds a prefix and a suffix.
 
awk '$0="eco.canadiana.ca/view/"$0' cleanlist.txt| awk '{print $0 "/1?r=0&s=1&fmt=json&api_text=1"}' > urlstograb.txt
 
# then if we want we can take those URLs and output them all to a big text file for analysis.
 
wget -i urlstograb.txt -O output.txt
