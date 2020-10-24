# Exfil	

## A challenge about XML vulnerabilities

![exfil](https://github.com/ReginaThePumpkin/HackDef4-writeups/blob/master/web/Exfil/img/1.png)

### Server: (http://3.19.72.219:3130)  

### When you get into the web site, you see an app to import XML files.
![website](https://github.com/ReginaThePumpkin/HackDef4-writeups/blob/master/web/Exfil/img/2.jpg)

### As the challenge was about to get the content of certain file inside the server, we could exploit a well-known XML vulnerability about malforming the requests with XML so that we add functionalities to the XML interpreter such as reading a local file and sending its content to an external server (/ etc / passwd).
![xml](https://github.com/ReginaThePumpkin/HackDef4-writeups/blob/master/web/Exfil/img/xml.png)

### In this file there are two important lines that get us the flag

This one that sets ´bar´ with the path wich interest us
``` XML
 <!ENTITY bar SYSTEM "file:///app/app/flag.txt" >]>
```
And this one, that gets the content on the file to show on the web page c:
``` XML
<nombre>&bar;</nombre>
``` 

So... the content of the flag was: ´hackdef{d0_n0t_tru5t_xml_f1l3s}´