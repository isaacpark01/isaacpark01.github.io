---
title: Homelab SSO Dropbox docs
date: 2023-09-02 12:00:00 +0000
categories: [homelab, SSO, DropBox, MFA]
tags: [duo,sso, jumpcloud]
---
# Welcome to DUO Ubuntu doc!
# # 🧾 Description
- - Use JumpCloud to create an SSO portal and integrate 1 SAML application for login
- purpose to create a user to be able to use SSO(Single Sign On), also use SAML(Security Assertion Markup Language)
- I will be using Dropbox instead for the process. 
- 

## 🌐 Action to perform 
1. Get a JumpCloud account and do it with


2. I decided to do Dropbox instead for a instant and cheaper way of doing this. 
#DROPBOX
3. I had first to get the  IDP URL (default) the x.509 certificate downloaded from jumpcloud
![hada_prompt_4_dropboxjcinfo.png](/images/photos/hada_prompt_4_dropboxjcinfo.png)

![hada_prompt_4_dropbox_certlink.png](/images/photos/hada_prompt_4_dropbox_certlink.png)
4. place it dropbox IDP, sign in url and upload the cert 

![hada_prompt_4_dropboxsso.png](/images/photos/hada_prompt_4_dropboxsso.png)

I made sure to add to apply all  users to the group in jumpcloud which allowed to have single sign

![hada_prompt_4_ssologos1.png](/images/photos/hada_prompt_4_ssologos1.png)

I was able to make sure that i made the users for both jumpcloud and dropbox to have the same email. I used all dummy addresses that i have. 

![hada_prompt_4_totalsuccess.png](/images/photos/hada_prompt_4_totalsuccess.png)

This is where i got succes after doing a single sign on 

![hada_prompt_4_success.png](/images//photos/hada_prompt_4_success.png)