# Cazador-DirLister
Find Directory Listing in multiple hosts easily.


How to find directory listing for a single domain.

- You need an HTTP repeater/tool/script in any language
- List of directory names [pick one](https://github.com/danielmiessler/SecLists)

Then you have to issue http request to check if a given directory exitsts or not.

for example using curl :

```
curl http://website.com/books/
```

if the response status code = `200`

Then you have to check if the response contains directory listing match.

an easy pattern is `Index of /`

To spead the process you can use `wfuzz` a great tool to bruteforce the web.

using the following command 

```
wfuzz -c -z file,/my_list  --ss ndex.of http://site.com/FUZZ/
```

This is quick and easy , but you have to reveiew the results. and if you want to scan multiple domains you have to execute repeated  commands.




Here we are going to discuss and explain why the tool was created , and what it really does.

 **Summary**


The tool is a one of cazador suite , with index 31 among other tools.

 **Purpose**
 
*Cazador-DirLister* is just a tool to scan multiple hosts to find directory listing enabled .

This discusses how to Scan a target ips/domains to look for directory-listing for all and how the tool works .


**Environment**

Windows OS 7 and higher.



**Tutorial from scratch**
The tool works at least with one or more domain names or ips.

if you want to scan a bigger area , you can use the other [tool](https://github.com/cazadorsuite/cazador-sublister) to collect more sub domains.

After downloading the tool , Select single or multi domains ,Define the list file "attached" ,  Fill your targets and start the tool.

![Running](https://github.com/cazadorsuite/Cazador-DirLister/blob/master/src/Running.png?raw=true)


The tool allows to scan with `HEAD` method to reduce the load on the network.

 
 **How it works?**
 The tool creates a list of targets , loops through all of them , checks if the target is online via port 80/443/other-user-customized , if not , the target is skipped , if the target is available on both ports , HTTPS will be used.The tool uses head to avoid much traffic on the network.
 
 **Why to use among other brute-forcing tools**
 - Smarter
 - Generate less traffic
 - Multiple targets at once.
 - No dependencies requires
 - Works on windows only :(
 
The assets on screenshot are public by  intention   , if you think this should be redacted , feel free to contact me.

[Check other tools](https://github.com/cazadorsuite)

