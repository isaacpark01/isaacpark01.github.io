---
created:
  - "{{date:YYYY-MM-DD}} {{time:HH:mm}}"
tags:
  - ISAAC
  - PARK/
---
# ❗ Information
Related to:: HADA
Tags:: DUO, MFA, Windows logon
# 🌌 Action plan -> 
---
# 🧾 Description
- Setting up a MFA for windows logon. I am going to use a vm. I don't want to use it on my personal computer 
- purpose to create a MFA when a USER tries to logon to their given system 
## 🌐 Action to perform 
1. Download the file first!
2. ![[Hada_prompt_2_download.png]]
From the first step in our earlier prompt, I would have to  setup the windows 10 vm to link with the logon situation with MFA
2. you would have to get the API hostname, integration key, and secret key from duo login. This would only work if you have this information placed into the installation. 
3. ![[hada_prompt_2_keys 1.png]]
 I was having trouble setting my MFA until i read the clear text saying that I had to match the profile along side with the user name. I used the usernames (hacker and parker)
![[HADA_logon_1.png]]