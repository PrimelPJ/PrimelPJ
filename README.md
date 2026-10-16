<div align="center">

<a href="https://github.com/PrimelPJ">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=28&duration=3000&pause=1000&color=00FF41&center=true&vCenter=true&width=550&lines=%24+who+am+i;Primel+Jayawardana;%24+nmap+-sV+--script+vuln;%24+tail+-f+%2Fvar%2Flog%2Fhoneypot.jsonl;%24+terraform+apply+-auto-approve" alt="Terminal typing animation" />
</a>

<br>

<h1>Primel Jayawardana</h1>

<p><b>CS @ University of Calgary</b><br>
<sub>Security Engineering · Threat Detection · Cloud Security · ICS/OT</sub></p>

[![Portfolio](https://img.shields.io/badge/primelj.dev-000?style=flat-square&logo=vercel&logoColor=white)](https://primelj.dev)
&nbsp;
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/primelj)
&nbsp;
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/PrimelJay)

<br>

![CompTIA Security+](https://img.shields.io/badge/CompTIA-Security%2B-C8202F?style=flat-square&logo=comptia&logoColor=white)
&nbsp;
![ICS 300](https://img.shields.io/badge/SANS-ICS%20300-0072C6?style=flat-square&logo=sans&logoColor=white)

</div>

<br>

I build security tools, threat detection systems, and hardened infrastructure.

Most of what I ship is defensive: honeypots that catch live attackers, SIEM rules that fire on brute force and password spray, cloud posture management that finds misconfigurations and auto-remediates them, and tamper-evident audit logs that prove nothing was altered. I also build at the infrastructure layer — distributed systems, ICS/SCADA security, and cloud-native backends on AWS and Azure.

Previously did compliance consulting at **TechHive Advisory** across Canada, the UAE, and Europe, and built ML data pipelines at **ReMotion Prosthetics** on Azure. Co-founding **Forq**, a food payment platform on Stripe Issuing and Flinks open banking.

<br>

## Featured

<table>
<tr>
<td valign="top">

### [Snare](https://github.com/PrimelPJ/snare) &nbsp; <sub>`Python` `Azure Sentinel` `Terraform` `WebSocket`</sub>

**Cloud honeypot with a live threat map.**

Runs fake SSH, Telnet, and web login services on an Azure VM. Bots find it within minutes and start guessing passwords. Every attempt is geo-tagged, shipped to Azure Log Analytics via managed identity, and drawn on a live world map as it happens. Four Sentinel analytics rules detect brute force, password spray, multi-protocol recon, and web exploit probes — each mapped to MITRE ATT&CK. One `terraform apply` builds the entire stack.

Nothing ever logs in. There is no shell behind any of the fake services.

</td>
</tr>
</table>

<br>

## Security & Detection

<table>
<tr>
<td width="50%" valign="top">

**[Threshold](https://github.com/PrimelPJ/threshold)**

Active Directory brute force defense lab. Four Vagrant VMs: a Windows Server 2022 DC, a domain-joined workstation, a Wazuh SIEM, and a Kali attacker. Custom Wazuh rules detect brute force, password spray, and account lockout with MITRE ATT&CK mapping. Active response auto-blocks repeat offenders.

`Wazuh` `Active Directory` `Vagrant` `PowerShell`

</td>
<td width="50%" valign="top">

**[Palisade](https://github.com/PrimelPJ/palisade)**

Multi-cloud security posture management for AWS and Azure. Scans for misconfigurations, auto-remediates them, and validates fixes with attack simulation. Continuous compliance checks against CIS benchmarks.

`Python` `AWS` `Azure` `Terraform`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Aegis](https://github.com/PrimelPJ/aegis)**

Tamper-evident audit log and streaming threat detection engine. Append-only event log with cryptographic chaining, Merkle tree batching, and Ed25519-signed checkpoints. Any modification to historical events is detected and pinpointed. A streaming rules engine evaluates every event on arrival. Zero external dependencies.

`Go` `Ed25519` `Merkle trees`

</td>
<td width="50%" valign="top">

**[Watchpost](https://github.com/PrimelPJ/watchpost)**

AWS account monitoring with auto-remediation. Watches CloudTrail for risky changes — public S3 buckets, open security groups, disabled logging — and fires Lambda functions to revert them automatically. EventBridge rules, SNS alerts, fully Terraformed.

`Python` `AWS Lambda` `CloudTrail` `Terraform`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[VaultKey](https://github.com/PrimelPJ/vaultkey)**

Automated secrets rotation engine on AWS. Rotates database credentials, API keys, and arbitrary secrets on a configurable schedule via Lambda and Secrets Manager. Designed as a drop-in compliance primitive for SOC 2 and ISO 27001 environments.

`Python` `AWS Lambda` `Secrets Manager`

</td>
<td width="50%" valign="top">

**[GRC Vendor Risk Engine](https://github.com/PrimelPJ/grc-vendor-risk-engine)**

Vendor risk scoring platform for GRC workflows. Ingests vendor questionnaires, scores risk across security, privacy, and operational dimensions, and flags vendors that fall below policy thresholds.

`Python` `Go` `PostgreSQL`

</td>
</tr>
</table>

<br>

## Infrastructure & Systems

<table>
<tr>
<td width="50%" valign="top">

**[Netwatch](https://github.com/PrimelPJ/netwatch-anomaly-detector)**

Distributed network anomaly detection. C++ packet capture, Java coordination layer, R statistical analysis. Detects port scans, beaconing, and traffic volume anomalies.

`C++` `Java` `R`

</td>
<td width="50%" valign="top">

**[NexusGuard](https://github.com/PrimelPJ/nexusguard)**

Distributed rate limiter with four algorithms (fixed window, sliding window, token bucket, leaky bucket) and Prometheus metrics. Protects APIs from abuse and DDoS at the edge.

`Python` `Redis` `Prometheus`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**[Carcajou](https://github.com/PrimelPJ/Carcajou)**

GNSS-denied vehicle navigation with a 15-state error-state Kalman filter. Stereo VO and LiDAR map matching. Drift under 0.01% over 120 s outages. Includes a synthetic test harness with CI-asserted accuracy.

`Python` `Kalman filter` `LiDAR`

</td>
<td width="50%" valign="top">

**[Beacon](https://github.com/PrimelPJ/Beacon1)**

Robot fleet telemetry platform. MQTT to AWS IoT Core, Kinesis hot path for live monitoring, Firehose cold path for S3 Parquet analytics. Fully Terraformed.

`ROS2` `AWS IoT` `Kinesis` `Terraform`

</td>
</tr>
</table>

<br>

## Stack

**Languages**

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![PowerShell](https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white)

**Security & Detection**

![Wazuh](https://img.shields.io/badge/Wazuh-3AABE6?style=flat-square&logo=wazuh&logoColor=white)
![Microsoft Sentinel](https://img.shields.io/badge/Sentinel-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![KQL](https://img.shields.io/badge/KQL-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Wireshark](https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white)
![Nmap](https://img.shields.io/badge/Nmap-0E83CD?style=flat-square&logo=nmap&logoColor=white)
![Kali Linux](https://img.shields.io/badge/Kali-557C94?style=flat-square&logo=kalilinux&logoColor=white)

**Cloud & Infrastructure**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=flat-square&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

**Robotics & ML**

![ROS 2](https://img.shields.io/badge/ROS%202-22314E?style=flat-square&logo=ros&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![ONNX](https://img.shields.io/badge/ONNX-005CED?style=flat-square&logo=onnx&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)

<br>

<br>
