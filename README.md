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
	wget https://openwall.info/wiki/_media/john/korelogic-rules-20100801.txt && cat korelogic-rules-20100801.txt >> /etc/john/john.conf


# Now do;
	john --stdout --wordlist=idc_just_johnme --rules:AppendYears,AppendCurrentYearSpecial,AppendSeason,Append4NumSpecial,Append3NumSpecial,Append2NumSpecial > Ownme.txt
	
# ssl scan a host .

	sslscan $ip
#POODLE vulnerability detection .. 

	nmap --script ssl-poodle -sV -p 443 $ip
# Nikto a host .
	nikto -h $ip -o result.html

# Finding vulnerability with wapiti

	apt install wapiti 
	wapiti -u $ip -o wapiti_result -f html -m all

	
# Do they have a WAF ?
	nmap -p 80,443 --script http-waf*
	wafw00f $ip
# DO They load balance?
	lbd $ip
