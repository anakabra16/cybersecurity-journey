# Project 04 — Mini SOC Lab

## Overview

A lightweight defensive security laboratory built to demonstrate a basic Security Operations Center (SOC) workflow using Windows 11 and Microsoft Sysmon.

The project follows:

**Generate → Collect → Detect → Investigate → Report**

## Objectives

- Collect Windows security telemetry
- Monitor process creation using Sysmon
- Monitor network connections using Sysmon
- Detect authentication failures
- Detect local account creation
- Investigate PowerShell activity
- Correlate network events with processes
- Document findings from a SOC analyst perspective

## Lab Architecture

```text
Windows 11
   |
   +-- Windows Security Event Log
   |      |
   |      +-- Event ID 4625 — Failed Logon
   |      |
   |      +-- Event ID 4720 — Account Creation
   |
   +-- Microsoft Sysmon
          |
          +-- Event ID 1 — Process Creation
          |
          +-- Event ID 3 — Network Connection
                    |
                    v
               Investigation
                    |
                    v
                 Reporting

