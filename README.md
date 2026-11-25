# Detection-as-code

## What is this repo for?

This repository contains detection rules for Microsoft Defender XDR / Advanced Hunting, in KQL. Every rule is its own YAML file that contains a query and metadata (ID, MITRE ATT&CK technique it covers, severity, etc.).

I test each rule against real data (sign-in data from a production M365 tenant that I administer). In the beginning my focus will be on brute force and password spray attacks because that is what I see the most in the Entra ID sign-in logs.

This repo is a work in progress. I will be adding rules one by one based on what I actually see in the tenant.
