# Homelab-Microsoft-Sentinel
Microsoft Sentinel, is a cloud native security information and event management (SIEM) and security orchestration, automation, and response (SOAR) solution that runs in the Azure cloud. It aims to enable holistic security operations by providing collection, detection, response, and investigation capabilities.

# Overview
To use Microsoft Sentinel, we need to create a virtual machine in Azure. In this VM, we will turn off the firewall. We want this VM to look enticing to attackers, and we want people to discover it quickly. We're going to create a log repository in Azure called a Log Analytics workspace, which will be used to ingest logs from the virtual machine. Then, we'll set up Azure Sentinel within Azure. It's essentially Microsoft's cloud-native SIEM, and we'll use it to create a map that shows all the different attacker data, allowing us to see the countries they originate from.

# Links
https://azure.microsoft.com/en-us/free/

https://github.com/joshmadakor1/Sentinel-Lab/blob/main/Custom_Security_Log_Exporter.ps1 (Script for log exporter)




