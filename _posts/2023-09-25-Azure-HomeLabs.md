---
title: Azure HomeLabs
date: 2023-09-25 12:00:00 +0000
categories: [homelab, azure]
tags: [homelab, azure]
---

# This is my homelab for Azure detection by making a fake threat

1. First create resources group
![resource_group.png](/images/photos/Azurelab/resource_group.png)

2. Creation OF VM and setting it up 
![create.png](/images/photos/Azurelab/create.png)

![VMSetup.png](/images/photos/Azurelab/VMSetup.png)

![vmdone.png](/images/photos/Azurelab/vmdone.png)

3. make sure to enable defender in azure 

![Enable.png](/images/photos/Azurelab/Enable.png)

![Workload.png](/images/photos/Azurelab/Workload.png)

4. Time to connect, during this time to enable just in time and allow access to your local machine

![Time.png](/images/photos/Azurelab/Time.png)

![connect.png](/images/photos/Azurelab/connect.png)

![timepart2.png](/images/photos/Azurelab/timepart2.png)


5. Time to use Sentienal, Cool name aint it haha

![setup_sentinel.png](/images/photos/Azurelab/setup_sentinel.png)

![sentinel.png](/images/photos/Azurelab/sentinel.png)

There are going to two logs

![Sentinel-log.png](/images/photos/Azurelab/Sentinel-log.png)

![Sentinel-logs1.png](/images/photos/Azurelab/Sentinel-logs1.png)

Make sure you do Window Security event, It may have  a different title every time. 

time to configure some rules 

![customrule.png](/images/photos/Azurelab/customrule.png)

![creationrule.png](/images/photos/Azurelab/creationrule.png)


6. Time to remote in my vm from my local host 

![RDCVM.png](/images/photos/Azurelab/RDCVM.png)

Enabling Security and 4624


![4624.png](/images/photos/Azurelab/4624.png)

We going to set up the logs for the setting it up automatically. 

```
SecurityEvent
| where EventID == 4624
| project TimeGenerated, Computer, AccountName
```

7. Setting up the Bait
![localsecuritypolicy.png](/images/photos/Azurelab/localsecuritypolicy.png)

![strigger.png](/images/photos/Azurelab/strigger.png)

![tasks.png](/images/photos/Azurelab/tasks.png)

![entity.png](/images/photos/Azurelab/entity.png)

![Completetion.png](/images/photos/Azurelab/Completetion.png)

FINISHED