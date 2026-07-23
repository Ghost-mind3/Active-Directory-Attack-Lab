# 🛡️ Enterprise Active Directory Attack Lab

> **Build, Attack, Detect & Secure an Enterprise Active Directory Environment from Scratch.**

![Windows Server](https://img.shields.io/badge/Windows%20Server-2019-blue)
![Active Directory](https://img.shields.io/badge/Active%20Directory-Lab-success)
![Status](https://img.shields.io/badge/Status-In%20Progress-orange)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📖 À propos du projet

Ce projet documente la création d'un environnement **Active Directory** réaliste dans le but d'apprendre et de maîtriser l'administration Windows ainsi que le **Pentest Active Directory**.

Contrairement à un simple laboratoire de tests, ce projet suit le cycle de vie complet d'une infrastructure d'entreprise :

- Concevoir une architecture Active Directory
- Déployer un Domain Controller
- Administrer les utilisateurs et les ressources
- Introduire des vulnérabilités réalistes
- Réaliser des attaques Active Directory
- Détecter les activités malveillantes
- Sécuriser et durcir l'infrastructure

L'objectif est de comprendre non seulement **comment exploiter une vulnérabilité**, mais également **pourquoi elle existe**, **comment la détecter** et **comment la corriger**.

---

# 🎯 Objectifs

Ce laboratoire a pour objectif de développer des compétences en :

- Windows Server Administration
- Active Directory Domain Services (AD DS)
- DNS
- Group Policy (GPO)
- SMB & NTFS Permissions
- AGDLP
- Service Accounts
- Kerberos
- Active Directory Security
- Active Directory Pentesting
- Detection Engineering
- Windows Hardening

---

# 🖥️ Infrastructure

Le laboratoire est actuellement composé des machines suivantes :

| Machine | Rôle |
|----------|------|
| **VULN-DC01** | Windows Server 2019 - Domain Controller |
| **VULN-CL01** | Windows 10 - Domain Workstation |
| **ATTACK01** | Debian - Attacker Machine |

Le laboratoire évoluera progressivement avec l'ajout de nouveaux serveurs (File Server, SQL Server, Web Server...) selon les besoins des scénarios.

---

# 🏢 Entreprise fictive

L'ensemble du laboratoire est construit autour d'une entreprise fictive :

**Nom :** VulnCorp

Secteur d'activité :

> Société de services informatiques

L'ensemble de l'infrastructure reproduit le fonctionnement d'une PME avec plusieurs départements, des utilisateurs, des groupes, des serveurs, des partages SMB, des Group Policies et des comptes de service.

---

# 🛣️ Roadmap

## Phase 01 — Server & Domain Configuration

- [x] Installation de Windows Server 2019
- [x] Configuration d'une adresse IP statique
- [x] Installation du rôle Active Directory Domain Services
- [x] Création de la Forest
- [x] Promotion du serveur en Domain Controller
- [x] Validation du domaine

---

## Phase 02 — Enterprise Design

- [ ] Architecture logique
- [ ] Organizational Units (OU)
- [ ] Naming Convention
- [ ] Security Groups
- [ ] Comptes administrateurs
- [ ] Comptes utilisateurs
- [ ] Service Accounts

---

## Phase 03 — Enterprise Administration

- [ ] Création des utilisateurs
- [ ] Création des groupes
- [ ] AGDLP
- [ ] Partages SMB
- [ ] NTFS Permissions
- [ ] DNS
- [ ] Group Policy
- [ ] Délégation d'administration

---

## Phase 04 — Active Directory Attack Simulation

- [ ] Password Spraying
- [ ] SMB Enumeration
- [ ] AS-REP Roasting
- [ ] Kerberoasting
- [ ] LLMNR Poisoning
- [ ] NTLM Relay
- [ ] BloodHound
- [ ] ACL Abuse
- [ ] Pass-the-Hash
- [ ] Pass-the-Ticket
- [ ] DCSync
- [ ] Lateral Movement

---

## Phase 05 — Detection & Hardening

- [ ] Sysmon
- [ ] Windows Event Forwarding
- [ ] Event Analysis
- [ ] Windows Defender
- [ ] Active Directory Hardening
- [ ] Security Best Practices

---

# 📂 Structure du projet

```text
Enterprise-Active-Directory-Attack-Lab
│
├── README.md
│
├── SERVER-DOMAIN-CONFIGURATION
│
├── ENTERPRISE-DESIGN
│
├── USERS-GROUPS
│
├── GROUP-POLICY
│
├── FILE-SERVER
│
├── SERVICE-ACCOUNTS
│
├── ATTACK-SCENARIOS
│
├── DETECTION
│
└── HARDENING
```

---

# 🎯 Philosophie du projet

Ce laboratoire suit une approche progressive.

Chaque fonctionnalité est développée selon le même processus :

1. Comprendre le fonctionnement
2. Déployer la fonctionnalité
3. Valider la configuration
4. Documenter les étapes
5. Introduire une mauvaise configuration
6. Exploiter la vulnérabilité
7. Détecter l'attaque
8. Corriger la vulnérabilité

L'objectif n'est pas seulement d'apprendre des commandes, mais de comprendre l'ensemble du cycle de vie d'une infrastructure Active Directory.

---

# 🛠️ Technologies

- Windows Server 2019
- Windows 10
- Debian Linux
- Active Directory Domain Services
- DNS
- SMB
- Kerberos
- LDAP
- PowerShell
- NetExec
- Impacket
- BloodHound
- Hashcat
- Responder
- Sysmon

---

# 📌 État du projet

🚧 **Projet en cours de développement**

Chaque phase est documentée au fur et à mesure de son implémentation afin de conserver une documentation fidèle à l'évolution du laboratoire.

---

## ⭐ Remerciements

Ce projet est réalisé dans un objectif d'apprentissage, de partage de connaissances et de développement de compétences en administration Windows, cybersécurité offensive et défense Active Directory.
