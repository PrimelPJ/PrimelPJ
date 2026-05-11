<div align="center">

# Primel Jayawardana

**CS @ University of Calgary &nbsp;|&nbsp; Backend · Distributed Systems · Fintech**

[![Portfolio](https://img.shields.io/badge/primelj.dev-000000?style=flat-square&logo=vercel&logoColor=white)](https://primelj.dev)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/primelj)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://instagram.com/primel_jayawardana_)

</div>

---

I build things at the infrastructure layer and ship them.

Currently co-founding **[Forq](https://github.com/PrimelPJ/forq)** — a food payment platform on Stripe Issuing and Flinks open banking. Before that: ML data pipelines at **ReMotion Prosthetics** on Azure, compliance consulting at **TechHive Advisory** across Canada, the UAE, and Europe, and a growing list of systems projects I build to actually understand how things work.

When I implement something, I read the paper first.

---

## Systems Projects

These exist because I wanted to understand how the infrastructure I use every day actually works.

---

### [raftdb](https://github.com/PrimelPJ/raftdb) &mdash; Distributed Key-Value Store

Built Raft consensus from scratch. Not a tutorial walkthrough — the actual algorithm: randomized leader election, majority-quorum log replication, fast log backtracking via conflict index hints, compare-and-swap, and safe re-election on leader failure.

The hard parts: stale RPCs from old terms arriving out of order, the "only commit current-term entries" safety rule (Section 5.4.2 of the paper), and livelock prevention. A 5-node cluster survives killing the leader and elects a new one without dropping a write.

```
PUT user:1  ->  Raft log  ->  quorum ack  ->  commit  ->  apply to KV
                 node0 LEADER
                 node1 FOLLOWER  AppendEntries RPC
                 node2 FOLLOWER  AppendEntries RPC
```

`Python · asyncio · pytest` &nbsp; **9/9 tests passing**

---

### [qstream](https://github.com/PrimelPJ/qstream) &nbsp; &mdash; Persistent Message Queue

SQS semantics built over a hand-rolled Write-Ahead Log. Every mutation is CRC32-checksummed and fsync'd before returning. Crash the process and restart — all unacked messages come back from the WAL replay.

Features: at-least-once delivery, visibility timeouts, dead-letter queues after N failures, priority heap (0-9), 5-minute deduplication window, delay queues, long polling, batch receive, and segment rotation at 64 MiB.

```
WAL record format:
[ MAGIC 4B ][ CRC32 4B ][ timestamp_ns 8B ][ len 4B ][ payload ]
                  ^
       verified on every replay. truncated tail = safe discard.
```

`Python · asyncio · pytest` &nbsp; **14/14 tests passing**

---

### [apexgateway](https://github.com/PrimelPJ/apexgateway) &nbsp; &mdash; API Gateway

Zero npm dependencies. Production-grade circuit breaker, hybrid rate limiter, and load balancer from scratch.

**Circuit breaker:** CLOSED / OPEN / HALF_OPEN state machine. Ring-buffer sliding window tracks failure rate in O(1). After a cooldown, sends probe requests before reopening traffic.

**Rate limiter:** Token bucket (burst control) combined with sliding window (rate smoothing) per identity key. Tier-aware — `default` and `premium` clients get different limits. Designed to swap the in-process store for Redis Lua scripts for multi-instance deployment.

**Load balancer:** Five strategies. Round robin, weighted (smooth Nginx algorithm), least connections, IP hash for sticky sessions, and Power of Two Choices — near-optimal distribution with O(1) overhead per request.

`Node.js · stdlib only` &nbsp; **17/17 tests passing**

---

## Product Projects

| Project | What it is | Stack |
|---------|-----------|-------|
| [**Forq**](https://github.com/PrimelPJ/forq) | Food BNPL + corporate meal card. Stripe Issuing card issuance, Flinks open banking, transaction ledger, group bill-splitting | React Native Expo, Node.js, PostgreSQL, Supabase, Stripe |
| [**Areej**](https://github.com/PrimelPJ/areej) | Islamic personal growth app. Quran reader, 9 hadith collections, 99 Names, 60+ duas, habit tracker, badges. Live on Vercel | React, Node.js, Supabase, Vite |
| [**Gym**](https://github.com/PrimelPJ/Gym) | iOS workout tracker. Streak tracking, volume stats, dark mode | Swift, SwiftUI, Core Data |
| [**GRC Vendor Risk Tool**](https://github.com/PrimelPJ/grc-vendor-risk) | Automated vendor risk scoring. Maps questionnaire responses to NIST CSF controls | Python, pandas |

---

## Stack

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white)
![Swift](https://img.shields.io/badge/Swift-F05138?style=flat-square&logo=swift&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

**Backend & Infra**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat-square&logo=express&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-635BFF?style=flat-square&logo=stripe&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white)

**Frontend & Mobile**

![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![React Native](https://img.shields.io/badge/React%20Native-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-000020?style=flat-square&logo=expo&logoColor=white)
![SwiftUI](https://img.shields.io/badge/SwiftUI-F05138?style=flat-square&logo=swift&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)

**Data & ML**

![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Azure Data Factory](https://img.shields.io/badge/Azure%20Data%20Factory-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)

---

## Stats

<div align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=PrimelPJ&show_icons=true&theme=dark&hide_border=true&count_private=true&include_all_commits=true&rank_icon=github" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=PrimelPJ&layout=compact&theme=dark&hide_border=true&langs_count=8&hide=jupyter%20notebook" />
</div>

<div align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=PrimelPJ&theme=dark&hide_border=true" />
</div>

---

<div align="center">
  <sub>Open to backend, SWE, and fintech internships for 2025/2026 &nbsp;·&nbsp; <a href="https://primelj.dev">primelj.dev</a></sub>
</div>
