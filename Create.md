For setting up a VM, you need to get an Azure subscription. They provide free 200 credits. Open azure portal and look for Virtual Machine.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/e83a6118-babe-4560-bfc5-134ef9223daf)

Click on Azure Virtual Machine.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/a51f5d62-ac4d-465a-b8fa-6b2f7ac25d68)

Furnish the required details to set up the VM

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/6c1b18f6-ada6-41a7-9d03-00035f85d1ee)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/cb1265a8-2534-4302-a38d-cddeee6902b6)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/9e1e4d54-dda2-4f96-84b2-f7065c8fdfc5)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/33119254-999c-4c6d-8fb9-a17da5bb4e5f)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/f578a84b-f366-446b-aab5-53cbfe32fbb2)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/91a436d3-c4e8-4347-b886-6d2c5461f8b2)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/3e01e5e5-ae9d-4d72-818b-cb01265d94db)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/543e89ae-ce2f-4b7c-97c3-e5db47100977)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/21ba7f4f-7859-4605-8e36-63c9bd809476)

Search for Log Analytics Workspace and proceed to create one.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/c1cbce29-3ab7-4d79-82c9-36c867fa3038)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/c142ca31-61e7-46e4-9e5b-62359709f3c3)

Search for Microsoft Defender for the Cloud; it helps us enable the ability to gather logs from the virtual machine into the Log Analytics workspace.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/8f0af6cc-39e2-43ec-a4d4-ef2718e71088)

Select the environmental settings option and turn on Azure Defender

Go to the Log Analytics Workspace and connect the virtual machine.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/c2b6cc69-49a2-487a-9293-d7a7813b60d0)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/4db4567f-107c-417b-867a-49276d96d007)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/ab7ef16b-dccf-424f-a360-2f1443684e0c)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/438a5ee9-79d9-4c97-8667-7bf5f4368257)

Now, to configure Microsoft Sentinel, which aids in visualizing potential cyber attacks.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/0f6503a1-0e6e-4ed9-b7d8-9596fc2a99af)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/b66bd4ae-6139-454c-9cef-eab117fdce3e)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/617d4ec2-a9f1-4fb1-b41f-24d51e98aefc)

We need to copy the IP address of the VM, as it will be used for logging in.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/daa66ac2-12ed-4ca1-bc47-54d1c5432bcc)

Log into Remote Desktop Connection paste the ip address and enter the credentials (select the option use a different account).

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/61abd28c-8cec-47d9-b83c-7d2560306590)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/085793ab-13a5-472d-8faf-6855464355b6)

In the VM, we need to turn off the firewall so that attackers can see our system. The vm basically acts as a honeypot. We need to copy a script. This script runs continuously in a loop. It looks through the security log, gathers all the events of people who failed to log in, including their IP addresses. Then, it retrieves their geodata and creates a new log file. We will use a website to get the locations. To do this, we need to get our API key, which is provided by the website when we log on to it.

Execute the script in Windows PowerShell. The log file looks like this 

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/7cdcf363-8b12-4288-b885-3770de51d49c)

The mentioned log file must be included in the Log Analytics Workspace. Create a custom log and paste the log file into the Log Analytics Workspace

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/a8ad2a5b-4a70-45bf-a0c8-6fa4a2b4d0a1)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/8c652c69-6d51-4c7e-951e-54055b73562a)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/36fdfc10-c9ac-4436-8aac-fd226a5db233)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/3d9c1a93-0505-47c0-a08f-0f35562e880d)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/ebeea12e-a244-4f50-8e10-944813179623)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/521e44b7-51b8-453b-bba7-3609e736df83)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/25253408-6e1f-461d-8262-ee7bcf2e0b58)

In Log Analytics Workspace, click on logs and paste the script, which essentially creates custom fields and extracts data from raw custom log data.

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/5715aaa5-d326-4878-ab46-bad4943dbec1)

Now, setting up a map in Sentinel with longitude or latitude,we can write a query where it shows where the attacks are originating from

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/766acdac-f26f-44aa-ae2c-5950eddc6763)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/e3c32587-7092-4278-9bf8-27742a46f445)

We can even edit the latitudes and longitude in the map settings

![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/e856442a-366e-4861-8cc0-028739faefe3)
![image](https://github.com/AlphaDeltaGamma/Homelab---Azure-Sentinel/assets/92504746/2526f842-a076-4e45-8bbf-e1046225eef6)


































































