# Intrusion detection and response

# The scenario
Jacqui, the security analyst for Yoyodyne's satellite office in Kalamazoo, is taking a much-needed vacation. Corporate has asked me to fill in for her while she enjoys some time on the 
beach. 

# My job
Analyze the alerts in the intrusion detection system, set up a SIEM to collect and analyze data, monitor systems for suspicious activity, document evidence and follow the incident
handling procedures to respond to any issues you uncover.

# Getting the environment set up
## 1. Confirm that the machine can run the project
## 2. Install VirtualBox 
## 3. Download project starter files

# Project instructions
## 1. Analyze alerts from the intrusion detection system using Sguil
Filter out alerts related to a honeypot. Of the remaining alerts, some appear to represent malicious behavior (true positives) and some appear to represent normal, or at least not particularly suspicious behavior (false positives). 

## 2. Live packet capture
Multiple Snort alerts were triggered by a single DNS request.
* Identify the DNS request in Sguil that triggered multiple alerts.
* Record the same request from the Security Onion VM using tcpdump.
* Save the file to dns.pcap 

## 3. Read and analyze packet captures
The Snort alerts may not tell the entire story. Remember that Snort can only alert on previously identified threats: new and unknown threats will not appear in Sguil! Use Wireshark to review related network traffic. For example, if this is a malware infection, are there any interesting signs of post-infection activity? Malware will frequently check in with a command-and-control server shortly after it is installed.

## 4. Create a snort rule
What if you hadn't seen the initial alert? There are a variety of reasons that could occur. If the host is a laptop, for example, the initial traffic could have occurred on an external network. Or the traffic could have been between systems on a segment of your network that isn't monitored. Create a Snort rule that will alert on the outbound connection (from the Yoyodyne network to the Internet) that you identified in the previous step.

## 5. Use Splunk to collect and analyze data
* Find the Zeek conn.log entry related to the suspicious activity identified in Step 1. Take a screenshot of the search query with the search result (there should be only one result) and save it as search.png
* Create a dashboard to identify privilege escalation. Identify both users who used sudo and the command or commands they ran. The dashboard should contain the following fields: _time, hostname, username, sudo_command. The events should be ordered by _time in ascending order (earliest time value first). Update the dashboard to display events from May 31, 2020. Take a screenshot of the dashboard and save as dashboard.png
* Create a report in Splunk to display authentication failures by user from the host-based logs. Run the report for May 31, 2020. Export the report and save as it as report.pdf

## 6. Use the incidentrResponse playbooks to determine the next steps
You have identified the initial indicator of compromise and performed additional analysis. What are the next steps to contain, eradicate, and recover from the threat?
Consult the Incident Response playbooks and find the most appropriate playbook. Follow the playbook and fill out the Containment, Analysis, and Recovery sections of the Incident Ticket. If a step involves contacting another party, such as the help desk, simply note that you contacted that party, the date and time, and the nature of the request.
Finally, note any recommendations to help better detect or prevent future occurrences of this threat in the Post-incident recommendations section of the Incident Ticket.
