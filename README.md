# Detection-as-code

## What is this repo for?

This repository contains detection rules for Microsoft Defender XDR / Advanced Hunting, in KQL. Every rule is its own YAML file that contains a query and metadata (ID, MITRE ATT&CK technique it covers, severity, etc.).

I test each rule against real data (sign-in data from a production M365 tenant that I administer). In the beginning my focus will be on brute force and password spray attacks because that is what I see the most in the Entra ID sign-in logs.

This repo is a work in progress. I will be adding rules one by one based on what I actually see in the tenant.

## Why am I working on this project?

While investigating sign-in logs I saw that around 10–15 accounts had 191 failed sign-in attempts. The attempts were made from IPs worldwide, including Indonesia, India, Russia, Nigeria and others. This prompted me to suspect a botnet. Attacks were a mix of brute force and password spray. There were repeated attempts against one account which triggered lockouts (error 50053), plus spray attempts across several accounts. Some attempts targeted Microsoft Azure CLI, which regular users do not use.

None of the attempts resulted in a successful sign-in but no alert fired either. I only found the attack by accident while practising KQL queries. An attack like this should trigger a detection rule automatically instead of relying on luck. That's why I'm building my rules as code.
