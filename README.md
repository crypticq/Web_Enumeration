# Web_Eunmration
Enumrate websites in a host

# Install 
	sudo apt install bing-ip2hosts

# run it

	bing-ip2hosts 'target ip' >> file
 
 
 # curl it (:
 
 	cat file | while read line; do curl -s $line; done | grep -Eo "(http|https)://[a-zA-Z0-9./?=_%:-]*"   
 
 # Password Profiling .
  
 	cewl -w $file -c -m 5 http://$target && cat $file | cut -d , -f 1 > idc_just_johnme
 
# Generate dic passowrd using john . 
first run this command <br />
	wget https://openwall.info/wiki/_media/john/korelogic-rules-20100801.txt && cat korelogic-rules-20100801.txt >> /etc/john/john.conf


# Now do;
	for ruleset in `grep KoreLogicRules /etc/john/john.conf | cut -d: -f 2 | cut -d\] -f 1 | grep Year | grep -v Special`; do john --stdout --wordlist=$file  --rules=${ruleset} ; done > o2 && cat o2 | cut -d , -f 1 > final_pass.txt

	
