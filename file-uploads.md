# file uploads

# File Extension Validation

~~~
$fileType = pathinfo($upload_path,PATHINFO_EXTENSION);
if($fileType == “php”) {
    die ("php files are not allowed");
}
~~~

Bypass:

Rename the file with another PHP extension

~~~
.php
.php3
.php4
.php5
~~~

Source: https://www.studyhost.net/support/knowledgebase/53/What-are-valid-file-extensions-I-can-use-for-PHP-scripts.html



# Mime Type Validation

MIME - Multipurpose Internet Mail Extensions
	- Used as an HTTP protocol to identify file formats and contents

Image MIME Type = image/jpeg
PHP file MIME Type = application/x-php


Bypass:

Spoof MIME using Burp, change to image/jpeg

![burp mime validation]['screenshots/burp.jpg']


# Other Bypasses

For more information about the above and other bypassess such as getimagesize():

https://www.virtualhackinglabs.com/?courses=7-7-file-upload-vulnerabilities

http://www.hackingarticles.in/5-ways-file-upload-vulnerability-exploitation


