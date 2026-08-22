# Lab Setup

## Overview

This document describes the infrastructure and configuration used to build the Mini SOC laboratory.

## Virtualization

- Hypervisor: VirtualBox
- Host OS: Windows
- Guest OS: Ubuntu Server 24.04 LTS

## Virtual Machines

| VM | Role | RAM | CPU | Network |
|---|---|---:|---:|---|
| Wazuh Server | SIEM / SOC Server | 4890 MB | 2 | NAT + Host-Only |
| Wazuh Agent | Monitored Endpoint | TBD | TBD | NAT + Host-Only |

## Network

The laboratory uses two network interfaces:

### NAT

Used by the virtual machines for internet access.

### Host-Only

Used for communication between the host machine and the virtual machines.

Network:

`192.168.56.0/24`

Wazuh Server:

`192.168.56.101`

Wazuh Agent:

`TBD`

## Architecture

```text
Host Machine
     |
Host-Only Network
192.168.56.0/24
     |
     +------------------+
     |                  |
Wazuh Server        Wazuh Agent
192.168.56.101      192.168.56.x
     |
     +-- Wazuh Manager
     +-- Wazuh Indexer
     +-- Wazuh Dashboard
