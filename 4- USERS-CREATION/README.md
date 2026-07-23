# 👤 Active Directory Users Creation

## 📌 Présentation

Cette étape consiste à créer les comptes utilisateurs et administrateurs dans l'environnement Active Directory du laboratoire **VulnCorp**.

Après avoir défini :

- l'architecture logique Active Directory dans **Enterprise Design** ;
- la structure des rôles et groupes dans **Groups Design** ;

cette phase permet de créer les identités qui composeront l'organisation.

L'objectif est de construire une base utilisateur réaliste avant la mise en place de la gestion des groupes, des permissions et des ressources.

---

# 🎯 Objectifs

Cette phase a pour objectifs :

- Créer les comptes utilisateurs de l'entreprise.
- Organiser les utilisateurs dans les bonnes **Organizational Units (OU)**.
- Créer les comptes administrateurs séparés des comptes standards.
- Appliquer une convention de nommage cohérente.
- Préparer l'environnement pour les futures phases d'administration et de Pentest Active Directory.

---

# 🌐 Active Directory Environment

Domaine :

```
vulncorp.local
```

Domain Controller :

```
VULN-DC01
```

---

# 🔑 Lab Password Configuration

Dans cet environnement de laboratoire, des mots de passe temporaires sont utilisés lors de la création des comptes.

## Standard Users

Mot de passe initial :

```
VulnCorp@2026!
```

---

## Administrative Accounts

Mot de passe initial :

```
Adm-VulnCorp@2026!
```

---

# 🔄 Password Change Requirement

Afin de simuler un environnement professionnel, les comptes sont configurés avec l'option :

```
User must change password at next logon
```

Le processus de création est donc :

```
Administrator creates account

        ↓

Temporary password assigned

        ↓

First user login

        ↓

Password change required
```

---

# 🏢 User Organization

Les comptes utilisateurs sont organisés selon les départements de l'entreprise.

Structure utilisée :

```
OU=Employees

├── IT

├── Finance

├── HR

├── Developers

├── Support

└── Management
```

Cette organisation permet :

- une meilleure gestion des identités ;
- une séparation logique des utilisateurs ;
- une préparation aux futures configurations **GPO**.

---

# 🖥️ IT Department

OU :

```
OU=IT,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| it.admin | Administrateur infrastructure |
| it.support | Technicien support |
| it.user | Utilisateur IT standard |

---

# 💰 Finance Department

OU :

```
OU=Finance,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| finance.manager | Responsable Finance |
| finance.user | Employé Finance |

---

# 👥 Human Resources Department

OU :

```
OU=HR,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| hr.manager | Responsable RH |
| hr.user | Assistant RH |

---

# 💻 Developers Department

OU :

```
OU=Developers,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| dev.lead | Responsable développement |
| dev.user | Développeur |

---

# 🛠️ Support Department

OU :

```
OU=Support,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| support.manager | Responsable support |
| support.user | Agent support |

---

# 🏢 Management Department

OU :

```
OU=Management,OU=Employees
```

Utilisateurs créés :

| Username | Description |
|---|---|
| ceo.user | Direction générale |
| manager.user | Responsable département |

---

# 🔐 Administrative Accounts

Les comptes administrateurs sont séparés des comptes utilisateurs standards afin de respecter le principe de séparation des privilèges.

OU :

```
OU=Admins
```

Comptes créés :

| Username | Description |
|---|---|
| adm.domain | Administration complète du domaine |
| adm.it | Administration infrastructure IT |
| adm.support | Administration support |

---

# 📷 Users Creation Screenshots

Les captures suivantes montrent la création des utilisateurs dans leurs Organizational Units respectives.

## IT Department

![IT Users Creation](Images/IT-Users-Creation.png)

---

## Finance Department

![Finance Users Creation](Images/Finance-Users-Creation.png)

---

## HR Department

![HR Users Creation](Images/HR-Users-Creation.png)

---

## Developers Department

![Developers Users Creation](Images/Developers-Users-Creation.png)

---

## Support Department

![Support Users Creation](Images/Support-Users-Creation.png)

---

## Management Department

![Management Users Creation](Images/Management-Users-Creation.png)

---

## Administrative Accounts

![Admin Accounts Creation](Images/Admin-Accounts-Creation.png)

---

# ✅ Validation

La création des utilisateurs peut être vérifiée avec PowerShell.

## Afficher les utilisateurs du domaine

```powershell
Get-ADUser -Filter *
```

---

## Vérifier les utilisateurs d'une OU spécifique

Exemple :

```powershell
Get-ADUser `
-SearchBase "OU=IT,OU=Employees,DC=vulncorp,DC=local" `
-Filter *
```

---

# 🔐 Security Perspective

Dans cette phase, aucune permission n'est encore attribuée aux utilisateurs.

La gestion est volontairement séparée en plusieurs étapes :

```
User Creation

        ↓

Group Membership

        ↓

Access Control

        ↓

Resource Permissions
```

Cette approche permet de conserver une architecture Active Directory claire et facilite l'analyse des droits lors des futures phases de Pentest.

---

# 📚 Skills

- Active Directory User Management
- Organizational Units Management
- Identity Management
- Account Provisioning
- Active Directory Administration

---

# 🚀 Next Step

La prochaine étape consistera à associer les utilisateurs aux **Security Groups** définis dans la phase précédente.

Objectif :

```
User Account

        ↓

Global Group

        ↓

Access Management
```

Cette étape permettra de commencer l'implémentation du modèle **AGDLP**.
