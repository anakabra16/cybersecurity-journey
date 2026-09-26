# Day 11 — Linux Process Security Audit

## Objective

The objective of this project was to perform a basic security audit of running processes on a Kali Linux system.

## Investigation Areas

- Running processes
- Process hierarchy
- CPU resource usage

## Commands Used

- `ps aux`
- `pstree -p`
- `ps aux --sort=-%cpu | head -15`

## Security Relevance

Process analysis helps security analysts understand what is currently running on a Linux endpoint and identify processes that may require further investigation.

## Ethical Scope

This investigation was performed locally on a controlled Kali Linux system for cybersecurity education.

No unauthorized systems were accessed or tested.
