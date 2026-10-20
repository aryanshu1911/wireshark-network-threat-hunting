# Network Threat Hunting and Incident Investigation Using Wireshark

An offline network traffic analysis project investigating a public RedLine Stealer training PCAP using Wireshark in Kali Linux.

## Project Overview

This project demonstrates a structured network threat hunting workflow, including packet inspection, protocol analysis, indicator extraction, evidence correlation, and defensive detection recommendations.

The analysis was performed offline. No malware was executed, and no live scanning or direct contact with observed external endpoints was performed.

## Objectives

- Analyse network protocols and TCP conversations.
- Investigate HTTP SOAP requests and responses.
- Identify relevant IP addresses, ports, hostnames, and application-layer indicators.
- Correlate packet numbers and timestamps into an evidence timeline.
- Develop Wireshark display filters and conceptual detection rules.
- Document false-positive considerations and incident response recommendations.

## Tools Used

- Kali Linux
- Wireshark 4.6.6
- capinfos
- sha256sum

## Key Findings

- Analysed a capture containing 8,807 packets over approximately 25.68 seconds.
- Observed `Endpoint/CheckConnect` and `Endpoint/GetUpdates` HTTP SOAP actions involving `188.190.10.10:55123`.
- Identified DNS and TLS activity involving `api.ip.sb` and `104.26.13.31`.
- Recorded indicators and supporting packet evidence.
- Developed display filters, defensive detection logic, and incident response recommendations.

These observations are based on the supplied training capture. They do not independently confirm credential theft, successful data exfiltration, or compromise of a real endpoint.

## Repository Contents

- `report/` — Final investigation report in PDF format.
- `evidence/` — Selected Wireshark evidence screenshots.
- `indicators/` — IOC register in CSV format.
- `detection/` — Wireshark display filters and defensive detection rules.

## Dataset

**Dataset source:** https://malware-traffic-analysis.net/2024/10/23/index.html

**PCAP file:** `2024-10-23-Redline-Stealer-infection-traffic.pcap`

The original PCAP and ZIP archive are not included in this repository; please obtain the dataset from the source page above.

## Evidence Integrity

SHA-256 of the analysed PCAP: `6498af315e9206c6ffc1ed5a488b28d1230c2fb44f2252bb5f05c3f8f68ce311`

## Disclaimer

This repository documents an educational network traffic investigation. Indicators are interpreted in context, and observed network activity should not be treated as definitive proof of maliciousness without corroborating evidence.
