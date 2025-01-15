# SIEM Lab

## Objective

The objective of this SIEM (Security Information and Event Management) lab is to provide hands-on experience in monitoring, analyzing, and responding to security events within an IT environment. I learned how to configure a SIEM solution, collect and aggregate log data from various sources, and identify potential security threats through event correlation and analysis. By the end of the lab, I have gained the skills necessary to leverage SIEM tools for threat detection, incident response, and compliance reporting.

### Skills Learned
- Search and Query Language
- Data Ingestion and Parsing
- Splunk Administration
- Alerting and Monitoring
- Knowledge Management
- Data Analysis and Reporting
- Dashboard Creation and Visualization
- Performance optimization
- Incident response and Forensics

### Tools Used
- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.

## Steps

1 ![BotS2 1](https://github.com/user-attachments/assets/12e9eb67-0d54-43a0-a549-c9469d64a8a0)
- Loaded Boss of the SoC version 2
- Initial search to find "Amber" as beginning source

2 ![BotS2 2](https://github.com/user-attachments/assets/f0794642-4a92-48c3-8a86-fe195919707a)
- Refined search query with "Ambers" visited IP address
- Removed identical query results
- Formatted results into table format

3 ![BotS2 3](https://github.com/user-attachments/assets/36641c8d-e56e-463b-b2e5-11822d6cbac3)
- Continued search for requested information
- Found competitor company through HTML search

4 ![BotS2 4](https://github.com/user-attachments/assets/511b6fb3-a2e7-4d3e-9f25-acef3cc5b413)
- Searched filenames for the ceo name
- file found under images with CEO name attached as part of image

5 ![BotS2 5](https://github.com/user-attachments/assets/14cc88cc-b272-4ffd-bb69-8a878f47838d)
- to find emails associated with Amber I changed source type to SMTP
- included berkbeer.com as an additional search query for refinement
- This search resulted in Ambers email
- With Ambers email, SMTP source, and Berkbeer.com as the qualifiers for search, I was able to narrow down to 4 results

6 ![BotS2 6](https://github.com/user-attachments/assets/21abd66e-9b77-4bca-a357-d741723237e8)
- With 4 results it was fairly easy to find Martin Berk as a full name
- with the full name under the same data set I found Martins email that Amber has used to contact him with
- Using the same raw data I found the additional email requested for an additional employee that was included in Ambers contacts

7 ![BotS2 7](https://github.com/user-attachments/assets/cd0fc017-80d1-44b8-91ab-4d5db770a34d)
- using ambers email and the additional contact I found earlier I am able to narrow down the search for the file that was emailed
- Utilizing the interesting fields I only have 1 with an attached file

8 ![BotS2 8](https://github.com/user-attachments/assets/d324f411-db60-4f9a-bf17-15d0a9b39e06)
- Following up for further information I am looking for Ambers personal email
- by decoding this email from base64 I find out her personal email was included in this code

9 ![BotS2 9](https://github.com/user-attachments/assets/27e1445a-0c20-49a0-89dd-e28999edfee1)
- Continuing to gather information I am looking for a browser that amber installed on a company machine
- by filtering via ambers name and ToR I am given to many results to manually search
- using the interesting fields I can filter it down to 4, which gives me which specific version she installed

10 ![BotS2 10](https://github.com/user-attachments/assets/56018e3a-5dad-43c7-8a32-a08472c70ad3)
- looking for further answers I am tasked with finding the public IP address for Brewertalk.com
- filtering with "brewertalk.com" and "dest_port=80" results in 2 IP address destinations
- the second IP address is the IP I am looking for

11 ![BotS2 11](https://github.com/user-attachments/assets/1141f5f0-f36d-45c9-83de-540e00602ab8)
- The next part was looking for an IP address that conducted a vuln scan
- Using the input of "brewertalk.com and filtering with interesting fields I get 6 results, which makes it easy to distinguish

12 ![BotS2 12](https://github.com/user-attachments/assets/1da4d644-dbd0-4440-a4b1-610e57cdc347)
- Using the IP addresses from above I can use them in the source ip field and then use interesting field to filter them down URI path
- Doing this I can verify what the IP address were accessing, allowing us to see attack vectors if any

13 ![BotS2 13](https://github.com/user-attachments/assets/8ed65f06-9575-4781-8d5f-457e661bdfe2)
- Next I'm looking for the SQL function that is being abused on the URI path
- Under the source IP search  and the URI path for /member.php I am able to start looking into items fields
- under the first item I can see updatexml within the form_data field

14 At this point the information needed shifts from Amber as the primary source to Kevin
- Just like with Amber I start with general information regarding Kevin
- Using just Kevin as the search term to simplify the results coming in

15 After gaining Kevins last name I can add in the modifier for XSS 
- with the XSS and Kevins name I can start looking for the username in the spear phishing attack

16 ![BotS2 16](https://github.com/user-attachments/assets/bee032e7-6586-4685-8aff-e5484e88d3d7)
- finalizing the query with the search terms: Kevin, http for the source type, and a URI path of any (*)
- by selecting the cookie field in the interesting fields category I get 1 option with the combined search terms
- this leaves me with 1 option for the cookie number

17 ![BotS2 17](https://github.com/user-attachments/assets/f6093c92-0931-4935-afa0-aba263b9c3fb)
- Next Im looking for a the username that was created via the spear phishing attack
- using the same results from the previous search I can look through the data field and find it under the destination header information




