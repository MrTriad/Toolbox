# Social Engineering
## Objectives 
  
   - Sniff user/employee credentials such as employee IDs, names, and email addresses
   - Obtain employees basic personal details and organizational information
   - Obtain usernames and passwords
   - Perform phishing
   - Detect phishing

### Vulnerabilities
- Insufficent security training
- No Role-based access 
- Fragmented organization structure
- Lacking security policies

----

### Sniff Credentials Using Social-Engineer-Toolkit ([SET](https://github.com/trustedsec/social-engineer-toolkit))

Used to draft email messages, attach malicious files and send them.
Allows simoultaneous use of Java applets, Metasploit browser and Harvester/Tabnabbing.

Here's an example of use:
After installing via python, launch the tool:


````
# setoolkit
````

Select "Social-Engineering Attacks " -> "Website Attack Vectors" -> "Credential Harvester Attack Method" -> "Site Cloner"

Now type IP of the POST back machine and the url of the target website.

After the target website is cloned, the POST back IP must be sent to the victim.
In order to do that we can craft a phishing e-mail.

Once the victim clicks on the link he/she will be prompted to the replica website. After entering the credentials, the victim will be redirected to the original website.
At the same time, SET will capture the credentials and display them in the terminal.

---

## Phishing Attack Detection 

---

## Tools
- [HTTrack](https://www.httrack.com/): It allows you to download a World Wide Web site from the Internet to a local directory, building recursively all directories, getting HTML, images, and other files from the server to your computer.
