# SOC-Automation-with-Shuffle
This project demonstrates an automated SOC workflow using Shuffle as the SOAR platform. It integrates Wazuh (open-source SIEM/XDR) to detect suspicious events, extracts file hashes from alerts via webhook, enriches them with VirusTotal threat intelligence, and creates alerts in TheHive for incident response.

![SOC Automation Project](https://github.com/user-attachments/assets/87707d65-c182-4d32-bda5-1b7392c26cb8)

## Architecture Overview

- **Orchestration:** Shuffle coordinates Wazuh, VirusTotal, and TheHive to enable automated alert handling  
- **Detection:** Wazuh monitors Windows logs and detects ASYNCRAT malware execution  
- **Ingestion:** Wazuh forwards alerts to Shuffle via webhook  
- **Processing:** Shuffle extracts the file hash (SHA-256) from alerts using regex  
- **Enrichment:** VirusTotal API is queried for hash reputation and threat details  
- **Response:** An enriched alert is created in TheHive for analyst investigation  

## Key Features

- **Automated Alert Ingestion:** Real-time alert forwarding from Wazuh to Shuffle via webhook  
- **Hash Extraction:** Regex-based extraction of SHA-256 hashes from Wazuh alert JSON (e.g., Sysmon events)  
- **Threat Intelligence Enrichment:** VirusTotal lookup for detection ratios and analysis reports  
- **Incident Creation:** Automatic alert creation in TheHive with enriched context  
- **Extensible Workflow:** Easily extendable to include notifications (Email, Slack, Discord), blocking actions, or additional enrichments  


