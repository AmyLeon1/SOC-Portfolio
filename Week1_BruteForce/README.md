# Week 1 - Brute Force Detection with Splunk

This project demonstrates a simple SSH brute-force attack simulation using Hydra, and how to analyze it with Splunk for SOC-style reporting.

---

## 1. Attack Simulation
Hydra was used to perform a brute-force attack on the target Ubuntu VM.

![Hydra Attack](screenshots/hydra_attack.png)

---

## 2. Raw Logs
A snippet of the target system's auth.log showing failed login attempts.

![Auth Log Snippet](screenshots/raw_logs.png)

---

## 3. Splunk Data Upload
The auth.log file was uploaded to Splunk, with Syslog source type and a dedicated `bruteforce` index.

![Splunk Upload](screenshots/splunk_source_type.png)

---

## 4. Raw Failed Login Events
Splunk search showing all failed login events from auth.log.
![Splunk Upload](screenshots/splunk_search.png)
```spl
index=bruteforce "Failed password"

