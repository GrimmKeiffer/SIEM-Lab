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

![BotS2 1](https://github.com/user-attachments/assets/12e9eb67-0d54-43a0-a549-c9469d64a8a0)
- Loaded Boss of the SoC version 2
- Initial search to find "Amber" as beginning source

![BotS2 2](https://github.com/user-attachments/assets/f0794642-4a92-48c3-8a86-fe195919707a)
- Refined search query with "Ambers" visited IP address
- Removed identical query results
- Formatted results into table format

![BotS2 3](https://github.com/user-attachments/assets/36641c8d-e56e-463b-b2e5-11822d6cbac3)
- Continued search for requested information
- Found competitor company through HTML search

![BotS2 4](https://github.com/user-attachments/assets/511b6fb3-a2e7-4d3e-9f25-acef3cc5b413)
- Searched filenames for the ceo name
- file found under images with CEO name attached as part of image

![BotS2 5](https://github.com/user-attachments/assets/14cc88cc-b272-4ffd-bb69-8a878f47838d)
- to find emails associated with Amber I changed source type to SMTP
- included berkbeer.com as an additional search query for refinement
- This search resulted in Ambers email
- With Ambers email, SMTP source, and Berkbeer.com as the qualifiers for search, I was able to narrow down to 4 results

![BotS2 6](https://github.com/user-attachments/assets/21abd66e-9b77-4bca-a357-d741723237e8)
- With 4 results it was fairly easy to find Martin Berk as a full name
- with the full name under the same data set we find Martins email that Amber has used to contact him with
- Using the same raw data we find the additional email requested for an additional employee that was included in Ambers contacts

![BotS2 7](https://github.com/user-attachments/assets/cd0fc017-80d1-44b8-91ab-4d5db770a34d)
- using ambers email and the additional contact I found earlier I am able to narrow down the search for the file that was emailed
- Utilizing the interesting fields we only have 1 with an attached file

![BotS2 8](https://github.com/user-attachments/assets/d324f411-db60-4f9a-bf17-15d0a9b39e06)
- Following up for further information I am looking for Ambers personal email
- by decoding this email from base64 we do find out her personal email was included in this code

![BotS2 9](https://github.com/user-attachments/assets/27e1445a-0c20-49a0-89dd-e28999edfee1)
- Continuing to gather information I am looking for a browser that amber installed on a company machine
- by filtering via ambers name and ToR I am given to many results to manually search
- using the interesting fields I can filter it down to 4, which gives me which specific version she installed

![BotS2 10](https://github.com/user-attachments/assets/56018e3a-5dad-43c7-8a32-a08472c70ad3)
- looking for further answers I am tasked with finding the public IP address for Brewertalk.com
- filtering with "brewertalk.com" and "dest_port=80" results in 2 IP address destinations
- the second IP address is the IP I am looking for
