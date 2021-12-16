## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:
Karl Fitzgerald Chairman
- How can this information be helpful to an attacker:
Attacke use CEO email to send a malasious link to gain acees in to the organization network. 

#### Step 2: DNS and Domain Discovery


Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: 
  
  9725 Datapoint Drive, Suite 100
  City:           San Antonio
  StateProv:      TX
  PostalCode:     78229
  Country:        US
  2. What is the NetRange IP address:

  65.61.137.64 - 65.61.137.127
  3. What is the company they use to store their infrastructure:

  Rackspace Backbone Engineering (C05762718)
  4. What is the IP address of the DNS server:

  65.61.137.117
#### Step 3: Shodan

- What open ports and running services did Shodan find:

80Apache Tomcat/Coyote JSP engine, 443Apache Tomcat/Coyote JSP engine, 8080Apache Tomcat/Coyote JSP engine,SSL Certificate

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 

marketplace search xss
recon/domains-vulnerabilities/xssed
marketplace install recon/domains-vulnerabilities/xssed

- Set the source to `demo.testfire.net`.

 options set SOURCE demo.testfire.net
- Run the module.

run
Is Altoro Mutual vulnerable to XSS: 

yes it is vulnerable summery fornd 1 total (1new)


### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:

On Zenmap screen, click Scan menu, 
select Save Scan  Select File Type: Nmap text format (.nmap). in command line, run nmap -T4 -A 192.168.0.10 -oN zenmapscan.txt

- Zenmap vulnerability script command: 

Click the Profile tab at the top and select Edit Selected Profile.
Click on the Scripting tab and view all the scripts that start with ftp.
Select the ftp-vsftpd-backdoor script by placing a check in the box.
Click Save Changes to save the profile settings.

- Once you have identified this vulnerability, 

answer the following questions for your client:
  1. What is the vulnerability:

  2. Why is it dangerous:

  The concept of the attack on VSFTPD 2.3.4 is to trigger the malicious vsf_sysutil_extra(); function by sending a sequence of specific bytes on port 21, which, on successful execution, results in opening the backdoor on port 6200 of the system and running as root.

  3. What mitigation strategies can you recommendations for the client to protect their server:

  The vsFTPd 2.3.4 backdoor reported on 2011-07-04 (CVE-2011-2523). The VSFTPD 2.3.4 service vulnerability is very unlikly an issue in a live situation because this version of VSFTPD is old nowadays and the vulnerable version was only available for one day.

A patch was released by Microsoft for SMB vulnerabilities in March 2017. Apply SMB patch is the best solution for Samba.

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.  

