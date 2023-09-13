---
created: ["{{date}} {{time}}"]
tags:
- AP/
---

# ❗ Information
Related to:: HADA 
Tags:: JUMPCLOUD, HADA, SSO, SAML 

# 🌌 Action plan -> 
---

# 🧾 Description
- - Use JumpCloud to create an SSO portal and integrate 1 SAML application for login
- purpose to create a user to be able to use SSO(Single Sign On), also use SAML(Security Assertion Markup Language)
- I wasn't able to complete this prompt with M365 because i don't have a functioning website to work with, but i will be using Dropbox instead for the process. 
- 

## 🌐 Action to perform 
1. Get a JumpCloud account and do it with![[hada_prompt_4_azure_activedirectory 1.png]]![[hada_prompt_4_azure_group.png]] a sso and integrate 1 saml
2. ![[hada_prompt_4_azure_fillin 1.png]]fill in your domain with an actual website that will work with Jumpcloud and M365
3.![[hada_prompt_4_azure_windowsconfi.png]]
I have to configure the service provider which will allow access from m365 to jumpcloud. I ran these commands. I would have to connect to the Azure AD. 

```
Install-Module MSOnline(install az ad module)
Connect-MSOLService(connect to az AD)
Install-Module ExchangeOnlineManagement(exchangeonlinemanagment)
Set-ExecutionPolicy RemoteSigned(Remote sign in )
Connect-Exchange(connect to microsoft exchange)
```

![[hada_prompt_4_azure_configuresp.png]]
4. I got stuck right around connect-exchangeonline due to not having a domain and that was verified.   
5. ![[hada_prompt_4_azure_import 1.png]]at this step, I have created two users, my own name along side with parker(alias)
6. I decided to do Dropbox instead for a instant and cheaper way of doing this. 
#DROPBOX
1. I had first to get the  IDP URL (default) the x.509 certificate downloaded from jumpcloud
![[hada_prompt_4_dropboxjcinfo.png]]![[hada_prompt_4_dropbox_certlink.png]]
2. place it dropbox IDP, sign in url and upload the cert 
![[hada_prompt_4_dropboxsso.png]]
I made sure to add to apply all  users to the group in jumpcloud which allowed to have single sign
![[hada_prompt_4_ssologos 1.png]]
I was able to make sure that i made the users for both jumpcloud and dropbox to have the same email. I used all dummy addresses that i have. 
![[hada_prompt_4_total success.png]]
This is where i got succes after doing a single sign on 
![[hada_prompt_4_success.png]]