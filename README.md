This write up is for TryHackMe Content Discovery:

This is one of my favorite parts of haking. digging through web pages or websites to find information. 

The answers are in the first paragraph. See if you can find it first.

What is the Content Discovery method that begins with M?
Manually

What is the Content Discovery method that begins with A?
Automated 

What is the Content Discovery method that begins with O?
OSINT 

Robots.txt:

Keep this in your back pocket. You will find fags or passwords hidden on robots.txt on THM. I had trouble getting the link to work on the kali box, it worked on my PC. 


What is the directory in the robots.txt that isn't allowed to be viewed by web crawlers?
/staff-portal

Favicon 

This is good info. copy this command: curl https://static-labs.tryhackme.cloud/sites/favicon/images/favicon.ico | md5sum

Take this checksum, go to the link on the page: https://wiki.owasp.org/index.php/OWASP_favicon_database

hit control+f on the webpage search for the checksum. your find f276b19aabcb4ae8cda4d22625c6735f:cgiirc (0.5.9)

Sitemap

Go to the link given for me it's: http://10.10.187.48/sitemap.xml
the path you're looking for is the last one. 
<url>
<loc>http://10.10.187.48/s3cr3t-area</loc>
<lastmod>2021-07-19T13:07:32+00:00</lastmod>
<priority>0.80</priority>
</url>
</urlset>
What is the path of the secret area that can be found in the sitemap.xml file? 
Copy the s3cr3t-area from this for the answer.

HTTP Headers 
Copy the command from the page: curl http://10.10.187.48 -v
after that you're looking for:
< X-FLAG: THM{HEADER_FLAG}

 Framework Stack 
Follow the link to the website's home page. We need to look at the webpage's HTML code, to do this hit f12 or right-click and click inspect. At the bottom of the code you'll see:
<!--
Page Generated in 0.05820 Seconds using the THM Framework v1.2 ( https://static-labs.tryhackme.cloud/sites/thm-web-framework )-->
Going to the link above you'll find a link to 3 web pages. go to documents and that will tell you how to login. copy /thm-framework-login from this webpage and go back to the webpage you are hacking. the link I use is http://10.10.187.48/thm-framework-login. Just like the instructions say use admin for user and password.
THM{CHANGE_DEFAULT_CREDENTIALS}

Google Hacking / Dorking 
This is fun info.
What Google dork operator can be used to only show results from a particular site?
site:

Wappalyzer 
What online tool can be used to identify what technologies a website is running? 
Wappalyzer 

Wayback Machine 
This is a fun tool. Not that I think you need this.
What is the website address for the Wayback Machine?
https://archive.org/web/

GitHub 

What is Git? 
version control system.

S3 Buckets 

What URL format do Amazon S3 buckets end in? 
.s3.amazonaws.com

Automated Discovery 

I like to use dirb but if you copy any of the commands you'll get the answer. I use this command on every machine I've attacked.

What is the name of the directory beginning "/mo...." that was discovered?
/monthly
What is the name of the log file that was discovered?
/development.log
