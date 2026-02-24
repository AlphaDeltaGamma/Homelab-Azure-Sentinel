# Homelab-Microsoft-Sentinel
Microsoft Sentinel, is a cloud native security information and event management (SIEM) and security orchestration, automation, and response (SOAR) solution that runs in the Azure cloud. It aims to enable holistic security operations by providing collection, detection, response, and investigation capabilities.

# Overview
To use Microsoft Sentinel, I have created a virtual machine in Azure. I have disabled the firewall in this VM. I want this VM to look enticing to attackers, and want people to discover it quickly. I have created a log repository in Azure called a Log Analytics workspace, which will be used to ingest logs from the virtual machine. Then, I set up Azure Sentinel within Azure. It's essentially Microsoft's cloud-native SIEM, and i've used it to create a map that shows all the different attacker data, allowing us to see the countries they originate from.


# Links
Azure Account: https://azure.microsoft.com/en-us/free/

Script for log exporter: https://github.com/joshmadakor1/Sentinel-Lab/blob/main/Custom_Security_Log_Exporter.ps1 




