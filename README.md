# \# Untitled

# 

# \## 📌 Project Summary

# 

# This lab demonstrates a full security monitoring pipeline using \*\*Wazuh SIEM\*\*. It covers deployment, agent onboarding, and event generation across Windows and Linux systems. Industry data shows that endpoint telemetry remains the highest-value data source for detection, with over 70 percent of confirmed incidents correlating back to basic host events. This project replicates that workflow in a controlled lab environment.

# 

# \## 🧱 Infrastructure Architecture

# 

# \- \*\*Wazuh Manager\*\*: Ubuntu 25.10 Live Server

# \- \*\*Linux Agent\*\*: Ubuntu 22.04.5 Desktop GNOME

# \- \*\*Windows Agent\*\*: Windows 10 22H2

# \- \*\*Hypervisor\*\*: VMware Workstation

# \- \*\*Networking\*\*: Internal virtual network, same broadcast domain for all endpoints

# 

# This setup mirrors what most small to mid-size organizations (SMBs) run, where detection often depends on a mix of Windows and Linux logs feeding into a centralized SIEM.

# 

# \## 🚀 Deployment Overview

# 

# \### 1. Wazuh Server Deployment

# 

# \- Installed using the official All-in-One installer

# \- Verified operational components: Wazuh Manager, Filebeat, OpenSearch stack

# \- Confirmed dashboard accessibility and core services

# 

# \### 2. Endpoint Agent Deployment

# 

# \- \*\*Windows Agent\*\*

# &nbsp;   - Downloaded and registered via dashboard

# &nbsp;   - Service validated and activated

# \- \*\*Linux Agent\*\*

# &nbsp;   - Installed via shell script

# &nbsp;   - Configured manager address and started agent

# \- \*\*Local Agent (Agent 000)\*\*

# &nbsp;   - Verified through command-line agent control

# &nbsp;   - Dashboard filtered with `agent.id:000` for server-side telemetry

# 

# \## 🔍 Event Generation Scenarios

# 

# This lab focuses on high-signal events, not noise. These categories consistently generate the strongest detection value in real environments based on incident-response statistics.

# 

# \### Windows Event: Failed authentication attempt

# 

# Monitored failed login attempt on Windows agent. Alert captured unauthorized access attempt.

# 

# !\[Full alert details](screenshots/Windows\_Full\_login.png)

# 

# Full alert details

# 

# \### Linux Event: Privilege escalation attempt

# 

# A new user was created, added to the sudo group, given a password, then logged in. The SIEM flagged the entire escalation chain, showing an account moving from normal user to full admin privileges.

# 

# !\[Full Path](screenshots/Ubuntu\_Priviledge\_Escalation\_Attack\_Path.png)

# 

# Full Path

# 

# Screenshots will be placed in a dedicated `/screenshots` folder.

# 

# \## 📊 What This Demonstrates

# 

# \- Ability to deploy and manage a production-style SIEM stack

# \- End-to-end telemetry flow across multiple operating systems

# \- Event detection logic aligned with real attacker behavior patterns

# \- Baseline host monitoring using Wazuh built-in modules

# 

# SIEM monitoring is statistically one of the top three baseline skills required for security operations and entry-level defensive roles. This lab reflects that workload accurately.

# 

# \## 📁 Repository Structure

# 

# ```powershell

# Wazuh-SIEM-Lab/

# ├── screenshots/        # Dashboard + alerts

# ├── logs/               # Exported alert logs

# └── \[README.md](http://readme.md/)           

# &nbsp;             

# ```

