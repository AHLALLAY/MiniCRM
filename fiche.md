# Spécifications du Projet CRM

## **Objectif du projet**
Créer un CRM simple et modulable avec **Laravel** (backend) et **Vue.js** (frontend).

Destiné aux agences (immobilier, marketing, freelance) pour gérer clients, prospects et suivis commerciaux.

---

## **Nom du CRM (propositions)**
- **Agency** – pour les agences modernes
- **SimplerCRM** – met l'accent sur la simplicité
- **Linkaro** – « link » pour les connexions, style moderne
- **Fidelo** – inspiré de la fidélisation client
- **Clientix** – combinaison de "client" + suffixe tech

---

## **Problématique résolue**
- Manque d'organisation dans la gestion des prospects
- Suivi manuel non centralisé (fichiers Excel, notes papier)
- Absence de visibilité sur les opportunités commerciales
- Difficulté de communication interne sur le statut des clients

---

## **Fonctionnalités (version 1 – manuelle)**

### **Gestion des clients**
Ajout, modification, suppression, liste filtrable et triable

### **Suivi des prospects**
Enregistrement manuel, notes, étapes de suivi, marquage comme "converti en client"

### **Suivi des actions**
Ajout de rendez-vous ou appels, historique des interactions

### **Documents**
Upload de fichiers (contrats, documents clients)

### **Authentification**
Connexion simple (pas de multi-compte SaaS)

### **Dashboard basique**
Statistiques sur clients/prospects, état des suivis

---

## **Palette de couleurs (2 couleurs max)**

### **Option 1**
**Bleu marine** (`#1E3A8A`) + **Vert menthe clair** (`#10B981`) – Professionnel et calme

### **Option 2**
**Violet foncé** (`#6D28D9`) + **Gris clair** (`#F3F4F6`) – Élégant et sobre

### **Option 3**
**Bleu clair** (`#3BB2F6`) + **Blanc cassé** (`#F9FAFB`) – Moderne et épuré

---

## **Définition d'un prospect**
Une personne ou entreprise montrant un intérêt potentiel mais n'ayant pas encore acheté.

### **Conditions pour considérer quelqu'un comme prospect :**
- Contact direct (email, appel)
- Remplissage d'un formulaire
- Identification proactive (prospection B2B)
- Intérêt montré (visites répétées sur le site, interactions sur les réseaux)
- Référence par un client

---

## **Différence entre contact, prospect et client**

| **Type** | **Définition** |
|----------|----------------|
| **Contact** | Donnée brute sans action |
| **Prospect** | Contact intéressé avec intention potentielle |
| **Client** | A signé un contrat ou acheté |

---

## **Signes d'intérêt d'un prospect**

### **Signes clairs**
- Contact direct
- Demande de devis
- Réponse à un message
- Acceptation d'un rendez-vous

### **Signes indirects**
- Visites multiples de pages
- Clics sur "Tarifs" ou "Contact"
- Interactions sur les réseaux sociaux

---

## **Gestion de la conversion prospect → client**

### **Structure des tables**
- **Table prospects** avec champ `converti` (booléen)
- **Table clients** pour les informations post-conversion

### **Logique de conversion**
1. Copie des données du prospect vers la table clients
2. Mise à jour ou suppression du prospect
3. **Option :** journal des conversions pour tracer l'historique

---

## **Demande pour le logo**

### **Informations nécessaires :**
- Nom du CRM
- Couleurs choisies
- Style souhaité (moderne, minimaliste, etc.)
- Éléments à inclure ou éviter (icône, texte, etc.)

---

## **Architecture technique suggérée**

### **Backend (Laravel)**
```
├── Models/
│   ├── User.php
│   ├── Contact.php
│   ├── Prospect.php
│   ├── Client.php
│   ├── Action.php
│   └── Document.php
├── Controllers/
│   ├── AuthController.php
│   ├── ContactController.php
│   ├── ProspectController.php
│   ├── ClientController.php
│   └── DashboardController.php
└── Migrations/
    ├── create_contacts_table.php
    ├── create_prospects_table.php
    ├── create_clients_table.php
    ├── create_actions_table.php
    └── create_documents_table.php
```

### **Frontend (Vue.js)**
```
├── components/
│   ├── Auth/
│   ├── Dashboard/
│   ├── Contacts/
│   ├── Prospects/
│   ├── Clients/
│   └── Common/
├── views/
│   ├── Login.vue
│   ├── Dashboard.vue
│   ├── ContactsList.vue
│   ├── ProspectsList.vue
│   └── ClientsList.vue
└── router/
    └── index.js
```

---

## **Base de données - Structure des tables**

### **Table: users**
- id (primary key)
- name (varchar)
- email (varchar, unique)
- password (varchar)
- created_at, updated_at

### **Table: contacts**
- id (primary key)
- nom (varchar)
- prenom (varchar)
- email (varchar)
- telephone (varchar)
- entreprise (varchar, nullable)
- statut (enum: 'contact', 'prospect', 'client')
- source (varchar, nullable)
- notes (text, nullable)
- created_at, updated_at

### **Table: prospects**
- id (primary key)
- contact_id (foreign key)
- niveau_interet (enum: 'faible', 'moyen', 'élevé')
- etape_suivi (varchar)
- date_dernier_contact (date)
- converti (boolean, default false)
- date_conversion (date, nullable)
- notes_suivi (text, nullable)
- created_at, updated_at

### **Table: clients**
- id (primary key)
- contact_id (foreign key)
- date_signature (date)
- valeur_contrat (decimal, nullable)
- statut_client (enum: 'actif', 'inactif', 'suspendu')
- notes_client (text, nullable)
- created_at, updated_at

### **Table: actions**
- id (primary key)
- contact_id (foreign key)
- type_action (enum: 'appel', 'email', 'rendez-vous', 'autre')
- description (text)
- date_action (datetime)
- statut (enum: 'planifié', 'réalisé', 'annulé')
- created_at, updated_at

### **Table: documents**
- id (primary key)
- contact_id (foreign key)
- nom_fichier (varchar)
- chemin_fichier (varchar)
- type_document (varchar)
- taille_fichier (integer)
- created_at, updated_at

---