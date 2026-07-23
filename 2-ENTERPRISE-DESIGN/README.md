# 🏢 Enterprise Active Directory Design

## 📌 Présentation

Cette phase consiste à concevoir l'architecture logique de l'environnement **Active Directory** avant la création des utilisateurs, groupes et ressources.

Dans un environnement professionnel, la structure Active Directory doit être définie avant le déploiement des objets afin de garantir :

- une administration simplifiée ;
- une meilleure organisation des ressources ;
- une application efficace des **Group Policy Objects (GPO)** ;
- une gestion correcte des permissions ;
- une base adaptée aux futurs scénarios de sécurité.

L'objectif de cette étape est donc de définir la structure du domaine **vulncorp.local** pour le laboratoire **VulnCorp**.

---

# 🎯 Objectifs

Cette phase a pour objectifs :

- Concevoir l'organisation logique du domaine Active Directory.
- Définir les **Organizational Units (OU)**.
- Éviter l'utilisation des conteneurs Active Directory par défaut.
- Préparer la future gestion des utilisateurs, ordinateurs et comptes de service.
- Définir une structure adaptée aux phases d'administration et de Pentest AD.

---

# 🌐 Domaine Active Directory

L'environnement utilise le domaine :

```
vulncorp.local
```

Le domaine représente l'infrastructure interne de l'entreprise fictive **VulnCorp**.

---

# 🏗️ Architecture logique Active Directory

La structure retenue est la suivante :

```
vulncorp.local
│
├── OU=Admins
│
├── OU=Employees
│   │
│   ├── OU=IT
│   ├── OU=Finance
│   ├── OU=HR
│   ├── OU=Developers
│   ├── OU=Support
│   └── OU=Management
│
├── OU=Endpoints
│   │
│   ├── OU=Workstations
│   └── OU=Servers
│
├── OU=Groups
│
└── OU=Service Accounts
```

---

# 🔎 Justification des choix

## OU=Admins

Cette OU contient les comptes utilisés pour l'administration de l'environnement.

Exemple :

```
adm.firstname.lastname
```

La séparation entre comptes utilisateurs standards et comptes administrateurs permet de respecter le principe de séparation des privilèges.

---

## OU=Employees

Cette OU regroupe les utilisateurs de l'entreprise.

Les utilisateurs sont ensuite séparés par département :

```
Employees

├── IT

├── Finance

├── HR

├── Developers

├── Support

└── Management
```

Cette organisation facilitera :

- l'application de GPO spécifiques ;
- la délégation d'administration ;
- la gestion des permissions.

---

## OU=Endpoints

Cette OU regroupe les machines appartenant au domaine.

Elle remplace l'utilisation du conteneur Active Directory par défaut **Computers**.

Structure :

```
Endpoints

├── Workstations

└── Servers
```

Cette séparation permet d'appliquer des configurations différentes selon le type de machine.

Exemple :

- GPO de sécurité pour les postes utilisateurs.
- GPO spécifiques pour les serveurs.

---

## OU=Groups

Cette OU sera utilisée pour centraliser les **Security Groups** Active Directory.

Ces groupes seront utilisés plus tard pour appliquer le modèle :

```
AGDLP

Accounts
    ↓
Global Groups
    ↓
Domain Local Groups
    ↓
Permissions
```

---

## OU=Service Accounts

Cette OU sera dédiée aux comptes utilisés par les services.

Exemples :

```
svc_sql

svc_backup

svc_web
```

Ces comptes seront utilisés dans les futurs scénarios de Pentest Active Directory :

- AS-REP Roasting
- Kerberoasting

---

# 📷 Architecture Active Directory

Le design logique du domaine a été défini avant la création des objets Active Directory.

![Active Directory Logical Design](Images/AD-Logical-Design.png)

---

# 🔐 Security Perspective

La conception de l'architecture Active Directory est une étape importante dans la sécurité d'un domaine.

Une mauvaise organisation peut entraîner :

- une mauvaise application des GPO ;
- une gestion complexe des permissions ;
- une augmentation des risques liés aux comptes privilégiés.

Cette structure servira de base pour introduire progressivement des configurations réalistes et analyser leur impact lors des phases de Pentest.

---

# 📚 Compétences mises en œuvre

- Active Directory Design
- Organizational Units (OU)
- Active Directory Administration
- Security Groups Planning
- Privilege Separation
- Enterprise Architecture

---


Cette étape permettra ensuite de mettre en place le modèle de permissions **AGDLP** et de préparer les futurs scénarios d'attaque.
