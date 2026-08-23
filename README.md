# Wazuh Security Lab

Practical cybersecurity laboratory focused on security monitoring,
detection, investigation, and MITRE ATT&CK mapping using Wazuh.

## Overview

This project documents the development of a practical Wazuh laboratory
designed to simulate security monitoring and detection scenarios in
Linux environments.

The goal is to understand the complete detection workflow:

Event → Detection → Investigation → MITRE ATT&CK

The laboratory is continuously evolving through controlled security
scenarios and documented investigations.

## Lab Architecture

### VM1 — Wazuh Server

- Operating System: Ubuntu Server 26.04 LTS
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

### VM2 — Linux Endpoint

- Operating System: Ubuntu Server 26.04 LTS
- Wazuh Agent
- SSH
- Linux system logs

## Network

| Component | IP Address |
|---|---|
| Wazuh Server | 192.168.56.101 |
| VM2 / Wazuh Agent | 192.168.56.105 |

## Scenarios

| # | Scenario | Status |
|---|---|---|
| 01 | SSH Authentication Failure | Completed |
| 02 | File Integrity Monitoring | Planned |
| 03 | User Account Creation | Planned |
| 04 | Privilege Changes | Planned |
| 05 | File Permission Changes | Planned |
| 06 | Suspicious Command Execution | Planned |
| 07 | Persistence Detection | Planned |
| 08 | SSH Brute Force Simulation | Planned |
| 09 | Security Event Investigation | Planned |
| 10 | Incident Investigation | Planned |

## Scenario 01 — SSH Authentication Failure

The first scenario focused on detecting failed SSH authentication
attempts against a monitored Linux endpoint.

The test generated controlled authentication failures using a
non-existent SSH user.

### Detection

The Wazuh environment identified the activity through SSH-related
rules.

- Rule 5710 — Level 5
- Rule 2502 — Level 10

### MITRE ATT&CK

The detected behavior was mapped to MITRE ATT&CK techniques including:

- T1110.001 — Password Guessing
- T1021.004 — SSH

### Investigation

The event was investigated through the Wazuh Dashboard using fields
such as:

- Agent name
- Agent IP
- Source IP
- Source user
- Decoder
- Full log
- Rule ID
- Rule level
- Fired times
- MITRE ATT&CK mapping

[View Scenario 01 →](scenarios/01-ssh-authentication-failure/README.md)

## Documentation

- [Lab Setup](documentation/lab-setup.md)
- [Troubleshooting](documentation/troubleshooting.md)

## Evidence

Screenshots and investigation evidence are organized inside each
scenario directory.

## Roadmap

The laboratory will progressively include additional detection and
investigation scenarios covering:

- File Integrity Monitoring
- User account monitoring
- Privilege changes
- File permission changes
- Suspicious command execution
- Persistence mechanisms
- SSH brute-force detection
- Event correlation
- Incident investigation

## Disclaimer
This laboratory is intended for educational and controlled testing
purposes. All security scenarios are performed within an isolated
virtual environment.
This laboratory is intended for educational and controlled testing
purposes. All security scenarios are performed within an isolated
virtual environment.
