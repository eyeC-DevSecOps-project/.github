![VMware](https://img.shields.io/badge/VMware-Virtualization-607078?logo=vmware\&logoColor=white)
![K3s](https://img.shields.io/badge/Kubernetes-K3s-326ce5?logo=kubernetes\&logoColor=white)
![Cilium](https://img.shields.io/badge/Cilium-eBPF-ffcc00?logo=cilium\&logoColor=black)
![eBPF](https://img.shields.io/badge/Linux-eBPF-000000?logo=linux\&logoColor=white)
![Security](https://img.shields.io/badge/Security-Zero--Trust-red)


# 👁️ eyeC(ybersecurity) ~ (... I see!) — Beyond Defense, Absolute Visibility


> *"Turning the invisible into actionable defense. A Closed-Loop Security Trilogy."*

L'écosystème eyeC est une suite de projets intégrés conçue pour démontrer la maîtrise du cycle de vie d'un incident de cybersécurité, de l'émulation de l'adversaire à la réponse automatisée au niveau du noyau (Kernel).

---

## 🏗️ L'Architecture de la Trilogie

Mon approche repose sur l'interconnexion de trois piliers fondamentaux :

### 1. 🛡️ Sovereign-Shield (The Enforcement Plane)

* **Rôle :** IPS (Intrusion Prevention System) & Orchestrateur de Quarantaine.
* **Technologies :** C++, Kubernetes (K3s), eBPF (Cilium), Ansible.
* **Innovation :** Capacité d'isoler des nœuds compromis en temps réel via des politiques réseau "Hardened" sans interruption de service.

### 2. 🛰️ Sentinel-Trace (The Intelligence Brain)

* **Rôle :** IDS (Intrusion Detection System) & Moteur de Corrélation.
* **Technologies :** C++, eBPF (Tetragon), MITRE ATT&CK Mapping.
* **Innovation :** Analyse comportementale au niveau du noyau Linux pour détecter des chaînes d'attaques complexes (ex: Reverse Shells) là où les outils traditionnels échouent.

### 3. 🌪️ Maelstrom-Breach (The Adversary Engine)

* **Rôle :** BAS (Breach & Attack Simulation) & Red Teaming.
* **Technologies :** C++, Python, Bash.
* **Innovation :** Automatisation de campagnes d'attaques multi-étapes (DDoS, SQLi, Ransomware) pour valider l'efficacité des boucliers défensifs.

---

## 🔄 Le Cycle de Validation "eyeC"

Voici comment les trois projets collaborent lors d'une simulation :

1. **ATTACK :** `Maelstrom-Breach` lance une campagne de Ransomware (`ransom_sim.cpp`).
2. **DETECTION :** `Sentinel-Trace` identifie un pic d'appels système suspects via ses hooks eBPF et corrèle l'activité.
3. **RESPONSE :** `Sentinel-Trace` envoie un signal critique à `Sovereign-Shield`.
4. **PROTECTION :** `Sovereign-Shield` exécute instantanément une isolation réseau du nœud cible.

---

## 🛠️ Stack Technique Globale

* **Languages :** C++17 (Performance), Python (Payloads), Bash (Automation).
* **Infra :** Kubernetes, Docker, Multi-OS (Debian, AlmaLinux, Windows).
* **Security :** eBPF/Tetragon, Cilium, MITRE ATT&CK, NIST Framework.
* **Ops :** Ansible (IaC), CMake, CI/CD.

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
