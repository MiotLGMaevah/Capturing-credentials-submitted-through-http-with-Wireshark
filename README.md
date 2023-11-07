# Capturing-credentials-submitted-through-http-with-Wireshark

Abstract:
-	During this Lab, I found that using HTTP on a site is very unsecure, especially if the website contains sensitive information and data that can be accessed through a login

Introduction:
-	HTTP does not encrypt data during client-to-server communication, which means that any data transmitted over HTTP is sent in plain text without any encryption or security mechanisms.
-	HTTP is very unsecure and should not be used on websites, especially if the website contains sensitive information and data that can be accessed through a login.
-	Wireshark is an easily accessible tool used to analyze packets; it can be used to look deep into communications happening on a network. 
-	In this Lab, I used my VM with Kali Linux to capture usernames and password that were submitted through http websites.

Experiment Details and steps:
1.	You first want to start your VM with Kali Linux 
2.	Open a terminal screen in Kali Linux and start Wireshark with the following command sudo wireshark
3.	When activated, Wireshark will ask you which interface you would like to use to capture packets. We will be using eth0 in this case.
-	You will be presented with 3 different screens/panels, although in the first part of this lab we will be focusing on the top/first screen to start capturing packets with their information such as packet number, source, destination and the time captured, it is important to know what the other screens represent; The second panel describes a hierarchical display of the information included in a single packet and the third panel displays the encoded packet data in its raw form.
4.	Using Firefox, visit the following site: http://testphp.vulnweb.com/login.php
-	The lock with the red line going through indicates that this page is communicating through http, meaning it is not encrypted and not safe.
5.	Enter a random username and password and click login. Then return to Wireshark. 
6.	You can end the packet capture in Wireshark by clicking the red square at the top. 
7.	Apply a display filter by typing in http in the box under the red square. This will only show http requests captured on Wireshark. 
8.	Look for the packet with POST included in the Info section of the first panel, once you find it click on that packet. 
9.	In the second panel, select the Hypertext Transfer Protocol and expand it to see the information it contains, then click on the HTML Form URL Encoded section to expand the information.
-	You will then see the username and password entered on the login form on the http website, it can also be viewed in raw farm in the third panel.

It is also possible for the captured data packets to be saved as a file for later analysis and for a report.


Conclusion:
-	My objective for this lab was to show how easy it is to capture credentials of a website using HTTP. I recommend the use of HTTPS for any website contain sensitive information that can be accessed through a simple login.

References:
https://www.101labs.net/comptia-security/lab-50-capturing-credentials-submitted-through-http-with-wireshark/ 

Acknowledgments:
-	I’d like to give Thanks to Mr. Paul Browning for providing Hands-on material for this lab and many others under his CompTIA Security+ Labs.

