---
created: ["{9/1/23}"]
tags:Sublime, security 
- AP/
---

# ❗ Information
Related to:: HADA
Tags::  Sublime, security, email 

# 🌌 Action plan -> 
---
 -   Set up Email Security with Sublime Security and showcase how to analyze
an email for a threat.

# 🧾 Description
- The first thing that i learned about analyzing an email was the basics:  email header, subject, body, grammar, and where the email was coming from. 
- Terms: that I have read upon are MUA(Mail User Agent), MTA(Message Transfer Agent) 
- Another that briefly that was I was learning about POP3, IMAP, SPF(Sender Policy Framework), X-accept, x-priority, xmsmail, x-mailer, x-mimeole, SMTP(Simple Mail Transport Protocol), ARC(Authenticated Received Chain), and DKIM(Domain Keys Identified Mail)
- pop3 focuses on one device, while IMAP focuses on the on multiple devices 
- SMTP focuses on the handling of sending the emails. 
- 
- 
- 

## 🌐 Action to perform 
The first thing that I am going to look are for ip address, the original email sender, what is being sent, what kinda file it is, time stamps, grammar mistakes, and domain. 
Innocent person: Rachael@tyrellcorp. io
Fake domain/email: robert.yi@globalleadership.o nrg
- Right now from X-received, its passing through the email servers, its being autheticated by ARC, the fake domain is using AMAZONSES as its primary provider for the email, which will allow it to pass since it comes from a reliable source. SPF along side with DKIM, it allows the user to go through because of the fact it came from a relaible domain, 
The real threat actor email: 01130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-west-3 .am azon ses. c o m
Return-Path: 01 130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-west-3.a mazonses.com
It will not be sent back to Robert.yi@globalleadership.o r g 
IP Address of origin: [23.251.246.2] which is located in france, it also explain the eu-west3(which represents the location of the data center)
File: html_smuggling_atob_high_entropy.shtml"
Its not  a trusted file, shmtl, this willl include intructions for the server, 
X-Priority: 1 focuses on the highest priority of an email message. 
Importance: 1
X-Mailer: Zimbra 8.7.11_GA_1854 (Zimbra-ZCO/8.7.10.1711 (6.1.7601 SP1 en-US)
 P158c T1508 R8502)
 this is the program that they wrote it on, zimbra
X-MimeOLE: Produced By Microsoft Exchange V6.5.7226.0
this is how they sent it from the outlook email app 


Delivered-To: rachael@tyrellcorp.i o
Received: by 2002:aca:bf55:0:0:0:0:0 with SMTP id p82csp2243973oif;
        Sun, 4 Dec 2022 07:29:31 -0800 (PST)
X-Google-Smtp-Source: AA0mqf4VHjy+pCZOrWdZqT42nAZm5gqfH34RnKvahUmpNS3MH3+SYLy4QtnuZlgFQfLBzwUGCxb0
X-Received: by 2002:a05:600c:a11:b0:3cf:8b53:747f with SMTP id z17-20020a05600c0a1100b003cf8b53747fmr45858985wmp.192.1670167771429;
        Sun, 04 Dec 2022 07:29:31 -0800 (PST)
ARC-Seal: i=1; a=rsa-sha256; t=1670167771; cv=none;
        d=google.com; s=arc-20160816;
        b=NFyBjrRq5lTXekHtJGp9hjPUqmTfMUA26maJBhPNpZfsJs/lMJj9qXdnHZ8DPTrFWJ
         v1BLfoD81H9LuhbfaYfh6RyGUgfG1nNslXq4ePqgMnFZ8Ux1scjeQoCDq1Uwl9WgMSfk
         XP3vdnVtfXneQxLNkwyb0iEO1sf+HnTX7nq7c61svGfNwbxoi3/0wGlvahl4lLe63gCp
         Fl17EMzbi3BIjZa4taL6cqI7OWtZXSyD79PeJIC/5GRbZeMk8jQpf6Ot0vgIWVRq9ZLI
         pcr3qYMGFcmS/fJxZVGeRfuZRQNGoG4+RUyI/s2ssI/w3cNXRepvIHSX6h+CLUyUjQth
         HHqg==
ARC-Message-Signature: i=1; a=rsa-sha256; c=relaxed/relaxed; d=google.com; s=arc-20160816;
        h=feedback-id:importance:message-id:date:subject:to:from:mime-version
         :dkim-signature;
        bh=+eAexosG9ohMKhhAOSQoNugpuLxSj1RjUSDydy3ASPg=;
        b=DBhZivFA7OqKXzkKetWMlZ/2l++dp1mRthXHbiWIjQ0gtvDlxtGHPgJ+ReEJz48bJG
         WyxAHaXIq9qe3uEjIQRnmsfJ3oNqOAfWRbT4W5U+F3faK4InM8iRqJszVNJfq6Z73B10
         iKC3VTUaMfQkocILeC4LA/CO9j2Z3IG5klQXBsAjTrfpBtcYNL33HZooChf7ZWjxEYxq
         Z3beOw8ktvRTjw6H9nP0cQiTlk4rxPhvlHnn2+I09aCdIIsFfyspZDCRV/Sd1hqP5Ylu
         pykeEna5q1ttuGAKmg2iHnPN+Si5DqPuPI5+zYJMxmLD3JiWYItPDXr7gjEsahecFQqf
         kL2g==
ARC-Authentication-Results: i=1; mx.google.com;
       dkim=pass header.i=@amazonse s.com header.s=4f4zjvqxldhskhj4hokzolcvnsn5qejk header.b=eii73B4P;
       spf=pass (google.com: domain of 0 1130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-wes t-3.amazonse s.com designates 23.251.246.2 as permitted sender) smtp.mailfrom=0113018 4ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-west -3.am azons es.com
Return-Path: <01130184 ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-w est-3.amazonses.com>
Received: from e246-2.smtp-out.eu-west-3.amazonses.com (e246-2.smtp-out.eu-west-3.amazonses.com. [23.2 51.246.2])
        by mx.google.com with ESMTPS id o10-20020a5d648a000000b00236cb3fec49si9410056wri.10.2022.12.04.07.29.30
        for <rachael@tyre llc orp.io
        (version=TLS1_2 cipher=ECDHE-ECDSA-AES128-GCM-SHA256 bits=128/128);
        Sun, 04 Dec 2022 07:29:31 -0800 (PST)
Received-SPF: pass (google.com: domain of 01130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-we st-3.amazonses.com designates 23.251.246.2 as permitted sender) client-ip=23.251.246.2;
Authentication-Results: mx.google.com;
       dkim=pass header.i=@ama zonses.com header.s=4f4zjvqxldhskhj4hokzolcvnsn5qejk header.b=eii73B4P;
       spf=pass (google.com: domain of 01130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-we st-3.amazonses.com designates 23.251.246.2 as permitted sender) smtp.mailfrom=01130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-we st-3.amazonses.com
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/simple;
	s=4f4zjvqxldhskhj4hokzolcvnsn5qejk; d=amazonses.com; t=1670167770;
	h=Content-Type:MIME-Version:From:To:Subject:Date:Message-ID:Feedback-ID;
	bh=+eAexosG9ohMKhhAOSQoNugpuLxSj1RjUSDydy3ASPg=;
	b=eii73B4Pylic6ZcOhH11U3mRKBRkoKgQS1ALc6bV8to5ELmHSAbBgQrFKYYl6oXc
	qDNLcu61bOqy0LWV/gLeUAXf8q6vlWyJWxOQGnWC6MfQ074ADbhHbC5y5J5iONKJhKe
	r0rFfht/RqXcerPysQmXL1uvH9+6CehuWz9WEmXc=
MIME-Version: 1.0
From: Human Resources <robert.yi@globalleadershi p.org
To: Rachael Tyrell <rachael@tyrellcorp. io
Subject: Review New Employee Benefits Enrollment
Date: Sun, 4 Dec 2022 15:29:30 +0000
Message-ID: <01130184ddc1b568-dddd0aa3-1a71-4961-8b8a-d38479a44212-000000@eu-we st-3.amazonses.com
X-Accept-Language: en-us, en
X-Priority: 1
Importance: 1
X-MSmail-Priority: Highest
X-Mailer: Zimbra 8.7.11_GA_1854 (Zimbra-ZCO/8.7.10.1711 (6.1.7601 SP1 en-US)
 P158c T1508 R8502)
X-MimeOLE: Produced By Microsoft Exchange V6.5.7226.0
Feedback-ID: 1.eu-west-3.JTW2QlH0gO8Qt98RbQDX87seJxC/978zXKleLTvW1Gk=:AmazonSES
X-SES-Outgoing: 2022.12.04-23.251.246.2
Content-Type: multipart/mixed; boundary=5c881faebd8bc180f75f9d3ea571f76c42568226239c798c9acc899a6a4c

--5c881faebd8bc180f75f9d3ea571f76c42568226239c798c9acc899a6a4c
Content-Type: multipart/alternative; boundary=2af6c5a77e6820b51ff0a70cdcee1bc4be5102c6bfab3e2b49ff1338fbba

--2af6c5a77e6820b51ff0a70cdcee1bc4be5102c6bfab3e2b49ff1338fbba
Content-Type: text/plain; charset=utf-8

Hello Rachael,

Please review and approve attached policy document at your earliest convenience.

-

Thanks,

Human Resources Department


