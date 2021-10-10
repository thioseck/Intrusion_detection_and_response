# Intrusion detection and response

# The Scenario
Jacqui, the security analyst for Yoyodyne's satellite office in Kalamazoo, is taking a much-needed vacation. Corporate has asked us to fill in for her while she enjoys some time on the 
beach. 

# Our Job
Analyze the alerts in the Intrusion Detection System, set up a SIEM to collect and analyze data, monitor systems for suspicious activity, document evidence and follow the incident
handling procedures to respond to any issues you uncover.

# Getting The Environment Set Up
## 1. Confirm That Your Machine Can Run The Project
## 2. Install VirtualBox 
## 3. Download Project Starter Files

# Project Instructions
## 1. Analyze Alerts from the Intrusion Detection System using Sguil
Filter out alerts related to a honeypot. Of the remaining alerts, some appear to represent malicious behavior (true positives) and some appear to represent normal, or at least not particularly suspicious behavior (false positives). 

## 2. Live Packet Capture
Multiple Snort alerts were triggered by a single DNS request.
* Identify the DNS request in Sguil that triggered multiple alerts.
* Record the same request from the Security Onion VM using tcpdump.
* Save the file to dns.pcap 

## 3. Read and Analyze Packet Captures
The Snort alerts may not tell the entire story. Remember that Snort can only alert on previously identified threats: new and unknown threats will not appear in Sguil! Use Wireshark to review related network traffic. For example, if this is a malware infection, are there any interesting signs of post-infection activity? Malware will frequently check in with a command-and-control server shortly after it is installed.
