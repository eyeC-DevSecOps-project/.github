### 🛠️ Engineering Stack
![C++](https://img.shields.io/badge/C%2B%2B-00599C?logo=c%2B%2B&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?logo=gnu-bash&logoColor=white) ![CMake](https://img.shields.io/badge/CMake-064F8C?logo=cmake&logoColor=white)

### 🛡️ Cyber & Intelligence
![MITRE ATT&CK](https://img.shields.io/badge/MITRE_ATT%26CK-FF6600?logo=matrix&logoColor=white) ![NIST](https://img.shields.io/badge/NIST_Framework-003366?logo=nist&logoColor=white) ![Cilium](https://img.shields.io/badge/Cilium-eBPF-ffcc00?logo=cilium&logoColor=black) ![eBPF](https://img.shields.io/badge/Linux-eBPF-000000?logo=linux&logoColor=white)

### ☁️ Infrastructure & Operating Systems
![K3s](https://img.shields.io/badge/Kubernetes-K3s-326ce5?logo=kubernetes&logoColor=white) ![Ansible](https://img.shields.io/badge/Ansible-EE0000?logo=ansible&logoColor=white) ![Kali Linux](https://img.shields.io/badge/Kali_Linux-557C94?logo=kali-linux&logoColor=white) ![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?logo=ubuntu&logoColor=white) ![Windows](https://img.shields.io/badge/Windows-0078D6?logo=windows&logoColor=white) ![AlmaLinux](https://img.shields.io/badge/AlmaLinux-D42028?logo=almalinux&logoColor=white) ![Debian](https://img.shields.io/badge/Debian-A81D33?logo=debian&logoColor=white) ![VMware](https://img.shields.io/badge/VMware-Virtualization-607078?logo=vmware&logoColor=white)

# 👁️ eyeC(ybersecurity) ~ (... I see!) — Beyond Defense, Absolute Visibility


> *"Turning the invisible into actionable defense. A Closed-Loop Security Trilogy."*

# 🛰️ The eyeC Project: A Closed-Loop Security Trilogy
> **"Turning the kernel-level invisible into actionable defense."**

The **eyeC Project** is an integrated cybersecurity ecosystem designed to demonstrate mastery over the full incident lifecycle: from **Adversary Emulation** to **Automated Kernel-Level Response**.



---

## 🏗️ The Trilogy Architecture

This ecosystem is built upon three fundamental pillars, interconnected to form a "Self-Healing" infrastructure.

### 1. 🛡️ [Sovereign-Shield](./Sovereign-Shield) (The Enforcement Plane)
* **Role:** IPS (Intrusion Prevention System) & Quarantine Orchestrator.
* **Stack:** C++, Kubernetes (K3s), eBPF (Cilium), Ansible.
* **Core Innovation:** Implements "Zero-Trust" micro-segmentation and real-time node isolation using eBPF-powered network policies without service downtime.

### 2. 🛰️ [Sentinel-Trace](./Sentinel-Trace) (The Intelligence Brain)
* **Role:** IDS (Intrusion Detection System) & Correlation Engine.
* **Stack:** C++, eBPF (Tetragon), MITRE ATT&CK Mapping.
* **Core Innovation:** A behavioral reasoning engine that ingests raw eBPF telemetry to detect complex attack chains (e.g., Reverse Shells or Ransomware patterns) directly within the Linux Kernel.

### 3. 🌪️ [Maelstrom-Breach](./Maelstrom-Breach) (The Adversary Engine)
* **Role:** BAS (Breach & Attack Simulation) & Red Teaming.
* **Stack:** C++, Python, Bash.
* **Core Innovation:** An automated campaign orchestrator that simulates multi-stage APT tactics (DDoS, SQLi, Data Exfiltration) to rigorously validate the defense trilogy's effectiveness.

---

## 🔄 The "eyeC" Validation Loop

The power of this trilogy lies in its synergy. Every defensive update is validated by an offensive simulation:

1.  **ATTACK:** `Maelstrom-Breach` executes a "Storm-Front" campaign, initiating a ransomware simulation (`ransom_sim.cpp`).
2.  **DETECTION:** `Sentinel-Trace` captures the spike in unauthorized system calls via eBPF and correlates the file-system activity.
3.  **REASONING:** The engine identifies a **MITRE T1486** technique and dispatches a critical signal to the enforcement plane.
4.  **RESPONSE:** `Sovereign-Shield` triggers an immediate network quarantine and kills the malicious process tree.



---

## 🛠️ Global Technical Stack

* **Languages:** C++17 (Performance Core), Python (Payloads), Bash (Automation).
* **Infrastructure:** Kubernetes, Docker, Multi-OS Lab (Debian, AlmaLinux, Windows).
* **Security Frameworks:** eBPF/Tetragon, Cilium, MITRE ATT&CK, NIST Cybersecurity Framework (Recover/Protect/Detect).
* **DevOps/IaC:** Ansible, CMake, CI/CD Pipelines.

---

## 🧭 Project Philosophy
Most security tools operate in silos. The **eyeC Project** breaks these silos by creating a **Feedback Loop** where offensive intelligence directly informs defensive posture. 

> *"To build a shield, you must first understand the storm."*

---


## 🧱 Architecture: Global View

```mermaid
graph TB
    %% Phase 1: Offensive Generation (Maelstrom Breach)
    subgraph Red_Team [🌪️ Maelstrom Breach: SIMULATE]
        ORCH[Simulation Orchestrator] --> BOTS[Distributed Bot Nodes]
        BOTS -->|Multi-Vector Attacks| INGRESS[Ingress Control Layer]
    end

    %% Phase 2: Observability (Sentinel Trace)
    subgraph Kernel_Layer [Linux Kernel]
        INGRESS --> HOOKS{eBPF Hooks}
    end

    subgraph Blue_Team_Trace [📡 Sentinel Trace: OBSERVE]
        HOOKS -->|Telemetry| TRACE[Sentinel Trace Engine]
        TRACE -->|Context Enrichment| REASON{Reasoning Engine}
    end

    %% Phase 3: Enforcement (Sovereign Shield)
    subgraph Blue_Team_Shield [🛡️ Sovereign Shield: ENFORCE]
        REASON -->|Suspicious Activity| POLICY{eBPF Policy Match}
        POLICY -->|DROP / REJECT| DROP[Kernel-Level Enforcement]
        POLICY -->|ALERT| ACTION[Automated Response]
    end

    %% Automation & Feedback Loop
    ACTION -->|Ansible Playbook| ISO[Node Isolation]
    ACTION -->|Hubble / Grafana| METRICS[Performance & Fidelity Metrics]
    ISO -.->|Purple Team Feedback| ORCH

    %% Styling
    style Red_Team fill:#1a0000,stroke:#ff4d4d,stroke-width:2px,color:#fff
    style Blue_Team_Trace fill:#001a33,stroke:#3399ff,stroke-width:2px,color:#fff
    style Blue_Team_Shield fill:#001a00,stroke:#00cc44,stroke-width:2px,color:#fff
    style HOOKS fill:#333,stroke:#fff,color:#fff

```

---

## ⚠️ Continuous Evolution Notice

The **eyeC** triplet—Sovereign-Shield, Sentinel-Trace, and Maelstrom-Breach—is currently under active and continuous development.

**Note:** This project is a living research framework. It is recommended to check the latest commits in each repository for the most up-to-date implementation details.


## 👤 Author

**O'djuma Badolo**  
Web Developer | Cybersecurity graduate | DevSecOps Enthusiast  
> *"Building secure systems by thinking like the storm."*
