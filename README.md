# SIEM Automation Pipeline (n8n)

## Overview
This project simulates a SOC automation workflow that ingests security alerts, enriches them with threat intelligence, and routes alerts based on severity.

## Architecture
Webhook → Parsing → VirusTotal → AbuseIPDB → Merge → Scoring → Routing → Slack

## Features
- VirusTotal enrichment (malicious/suspicious analysis)
- AbuseIPDB enrichment (abuse confidence, TOR detection)
- Severity scoring logic (LOW → CRITICAL)
- Alert deduplication
- Conditional routing (HIGH/CRITICAL → Slack alerts)
- Safe URL formatting (non-clickable indicators)

## Example Alert
- Source IP: 185[.]220[.]101[.]45
- VT Severity: HIGH
- Abuse Score: 100
- TOR Exit Node: True

## Technologies Used
- n8n (workflow automation)
- VirusTotal API
- AbuseIPDB API
- Slack API

## How to Run
1. Import workflow JSON into n8n
2. Add API keys (VirusTotal + AbuseIPDB)
3. Configure Slack webhook
4. Send test alerts via webhook

## Future Improvements
- Risk scoring engine (0–100)
- Shodan enrichment
- Persistent storage (database logging)
- Auto-response actions (block IP simulation)
