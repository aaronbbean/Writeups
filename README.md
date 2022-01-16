This write up is for TryHackMe Content Discovery:

This is one of my favorite parts of haking. digging through web pages or websites to find information. 

The answers are in the first paragraph. See if you can find it first.


Robots.txt:

Keep this in your back pocket. You will find fags or passwords hidden on robots.txt on THM. I had trouble getting the link to work on the kali box, it worked on my PC. 


Favicon 

This is good info. copy this command: curl https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico | md5sum

Take this checksum, go to the link on the page: https://wiki.owasp.org/index.php/OWASP_favicon_database

hit control+f on the webpage search for the checksum. your find f276b19aabcb4ae8cda4d22625c6735f:c@#$%^

Sitemap

Go to the link given for me it's: http://10.10.187.48/sitemap.xml
the path you're looking for is the last one. 
<url>
<loc>http://10.10.187.48/@#%&^%</loc>
<lastmod>2021-07-19T13:07:32+00:00</lastmod>
<priority>0.80</priority>
</url>
</urlset>
Cope the flag between <loc>http://10.10.187.48/ and </loc>

HTTP Headers 
Copy the command from the page: curl http://10.10.187.48 -v
after that you're looking for:
< X-FLAG: THM{@^^&%$#}

 Framework Stack 
Follow the link to the website's home page. We need to look at the webpage's HTML code, to do this hit f12 or right-click and click inspect. At the bottom of the code you'll see:
<!--
Page Generated in 0.05820 Seconds using the THM Framework v1.2 ( https://static-labs.tryhackme.cloud/sites/thm-web-framework )-->
Going to the link above you'll find a link to 3 web pages. go to documents and that will tell you how to login. copy /thm-framework-login from this webpage and go back to the webpage you are hacking. the link I use is http://10.10.187.48/thm-framework-login. Just like the instructions say use admin for user and password.
THM{@#&*$^&*%}

Google Hacking / Dorking 
This is fun info.
The answer is in the text.

Wappalyzer 
The answer is in the text.

Wayback Machine 
Copy the link.

GitHub 
The answer is in the text.

S3 Buckets 
The link is in the text.

Automated Discovery 

I like to use dirb but if you copy any of the commands you'll get the answer. I use this command on every machine I've attacked.

Copy the two referenced directories. the answer to the 2nd question ends in .log
