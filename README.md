# Web_Eunmration
Enumrate websites in a host

# Install 
sudo apt install bing-ip2hosts

# run it

bing-ip2hosts 'target ip' >> file
 
 
 # curl it (:
 
 cat file | while read line; do curl -s $line; done | grep -Eo "(http|https)://[a-zA-Z0-9./?=_%:-]*"   
