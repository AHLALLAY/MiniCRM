# User Stories - Projet CRM

## **Authentification et Accès**

### **US001 - Connexion utilisateur**
**En tant qu'** utilisateur de l'agence  
**Je veux** me connecter au CRM avec mes identifiants  
**Afin de** accéder aux données clients et prospects de manière sécurisée  

**Critères d'acceptation :**
- [ ] Je peux saisir mon email et mot de passe
- [ ] Le système vérifie mes identifiants
- [ ] Je suis redirigé vers le tableau de bord après connexion réussie
- [ ] Un message d'erreur s'affiche si les identifiants sont incorrects
- [ ] Ma session reste active pendant ma navigation

---

## **Gestion des Contacts**

### **US002 - Ajouter un contact**
**En tant qu'** commercial  
**Je veux** ajouter un nouveau contact dans le système  
**Afin de** centraliser toutes les informations de personnes intéressées  

**Critères d'acceptation :**
- [ ] Je peux saisir : nom, prénom, email, téléphone, entreprise
- [ ] Je peux ajouter une source (comment j'ai obtenu ce contact)
- [ ] Je peux ajouter des notes libres
- [ ] Le contact est automatiquement daté à la création
- [ ] Les champs obligatoires sont validés avant sauvegarde

### **US003 - Consulter la liste des contacts**
**En tant qu'** utilisateur  
**Je veux** voir tous mes contacts dans une liste  
**Afin de** avoir une vue d'ensemble et retrouver facilement une personne  

**Critères d'acceptation :**
- [ ] La liste affiche nom, prénom, entreprise, statut, date de création
- [ ] Je peux trier par nom, date, statut
- [ ] Je peux filtrer par statut (contact/prospect/client)
- [ ] Je peux rechercher par nom ou entreprise
- [ ] La pagination fonctionne si j'ai beaucoup de contacts

### **US004 - Modifier un contact**
**En tant qu'** utilisateur  
**Je veux** modifier les informations d'un contact existant  
**Afin de** maintenir les données à jour  

**Critères d'acceptation :**
- [ ] Je peux cliquer sur un contact pour l'éditer
- [ ] Tous les champs sont modifiables
- [ ] Les changements sont sauvegardés immédiatement
- [ ] L'historique de modification est conservé

### **US005 - Supprimer un contact**
**En tant qu'** utilisateur  
**Je veux** supprimer un contact obsolète  
**Afin de** maintenir ma base propre  

**Critères d'acceptation :**
- [ ] Une confirmation est demandée avant suppression
- [ ] Les données liées (actions, documents) sont également supprimées
- [ ] La suppression est irréversible et clairement indiquée

---

## **Gestion des Prospects**

### **US006 - Convertir un contact en prospect**
**En tant qu'** commercial  
**Je veux** marquer un contact comme prospect  
**Afin de** commencer un suivi commercial structuré  

**Critères d'acceptation :**
- [ ] Je peux changer le statut d'un contact vers "prospect"
- [ ] Je peux définir un niveau d'intérêt (faible/moyen/élevé)
- [ ] Je peux noter l'étape de suivi actuelle
- [ ] La date de conversion est automatiquement enregistrée

### **US007 - Suivre l'évolution d'un prospect**
**En tant qu'** commercial  
**Je veux** mettre à jour le statut de suivi d'un prospect  
**Afin de** garder une trace de l'avancement de la relation commerciale  

**Critères d'acceptation :**
- [ ] Je peux modifier l'étape de suivi (premier contact, devis envoyé, négociation, etc.)
- [ ] Je peux changer le niveau d'intérêt
- [ ] Je peux ajouter des notes de suivi
- [ ] La date de dernière modification est automatique

### **US008 - Convertir un prospect en client**
**En tant qu'** commercial  
**Je veux** marquer un prospect comme client  
**Afin de** finaliser le processus de conversion  

**Critères d'acceptation :**
- [ ] Je peux changer le statut vers "client"
- [ ] Je peux saisir la date de signature
- [ ] Je peux noter la valeur du contrat
- [ ] Le prospect apparaît maintenant dans la liste des clients
- [ ] L'historique de conversion est conservé

---

## **Gestion des Clients**

### **US009 - Consulter la liste des clients**
**En tant qu'** manager  
**Je veux** voir tous nos clients actuels  
**Afin de** avoir une vue sur notre portefeuille client  

**Critères d'acceptation :**
- [ ] La liste affiche nom, entreprise, date signature, valeur contrat
- [ ] Je peux filtrer par statut client (actif/inactif/suspendu)
- [ ] Je peux trier par date de signature ou valeur
- [ ] Je peux rechercher par nom ou entreprise

### **US010 - Mettre à jour un client**
**En tant qu'** commercial  
**Je veux** modifier les informations d'un client  
**Afin de** maintenir son dossier à jour  

**Critères d'acceptation :**
- [ ] Je peux modifier le statut du client
- [ ] Je peux mettre à jour la valeur du contrat
- [ ] Je peux ajouter des notes spécifiques client
- [ ] Les modifications sont horodatées

---

## **Suivi des Actions**

### **US011 - Planifier une action**
**En tant qu'** commercial  
**Je veux** programmer un appel ou rendez-vous avec un contact  
**Afin de** structurer mon suivi commercial  

**Critères d'acceptation :**
- [ ] Je peux choisir le type d'action (appel, email, rendez-vous, autre)
- [ ] Je peux définir une date et heure
- [ ] Je peux ajouter une description détaillée
- [ ] L'action apparaît comme "planifiée"
- [ ] Je peux associer l'action à n'importe quel contact

### **US012 - Marquer une action comme réalisée**
**En tant qu'** commercial  
**Je veux** confirmer qu'une action a été effectuée  
**Afin de** suivre mes activités commerciales  

**Critères d'acceptation :**
- [ ] Je peux changer le statut vers "réalisé"
- [ ] Je peux ajouter des notes sur le résultat
- [ ] La date de réalisation est enregistrée
- [ ] L'action n'apparaît plus dans mes tâches à faire

### **US013 - Consulter l'historique des actions**
**En tant qu'** utilisateur  
**Je veux** voir toutes les interactions avec un contact  
**Afin de** comprendre l'historique de la relation  

**Critères d'acceptation :**
- [ ] Les actions sont listées par ordre chronologique
- [ ] Je vois le type, date, description et statut de chaque action
- [ ] Je peux filtrer par type d'action ou période
- [ ] L'historique est accessible depuis la fiche contact

---

## **Gestion des Documents**

### **US014 - Uploader un document**
**En tant qu'** utilisateur  
**Je veux** associer un fichier à un contact  
**Afin de** centraliser tous les documents (contrats, devis, etc.)  

**Critères d'acceptation :**
- [ ] Je peux sélectionner un fichier depuis mon ordinateur
- [ ] Les formats PDF, DOC, JPG, PNG sont acceptés
- [ ] La taille maximum est de 10MB
- [ ] Le nom du fichier et la date d'upload sont enregistrés
- [ ] Une confirmation de succès s'affiche

### **US015 - Consulter les documents d'un contact**
**En tant qu'** utilisateur  
**Je veux** voir tous les fichiers liés à un contact  
**Afin de** retrouver rapidement un document  

**Critères d'acceptation :**
- [ ] Les documents sont listés avec nom, type, date, taille
- [ ] Je peux télécharger chaque document
- [ ] Je peux supprimer un document (avec confirmation)
- [ ] Les documents sont triés par date (plus récent en premier)

---

## **Tableau de Bord**

### **US016 - Visualiser les statistiques**
**En tant qu'** manager  
**Je veux** voir un résumé de l'activité commerciale  
**Afin de** suivre les performances de l'équipe  

**Critères d'acceptation :**
- [ ] Je vois le nombre total de contacts, prospects, clients
- [ ] Je vois le nombre de conversions du mois
- [ ] Je vois les actions planifiées pour aujourd'hui
- [ ] Je vois un graphique d'évolution des conversions
- [ ] Les données sont mises à jour en temps réel

### **US017 - Voir mes tâches du jour**
**En tant qu'** commercial  
**Je veux** voir mes actions planifiées pour aujourd'hui  
**Afin de** organiser ma journée de travail  

**Critères d'acceptation :**
- [ ] Les actions du jour sont listées par ordre chronologique
- [ ] Je vois le contact associé, type d'action et heure
- [ ] Je peux marquer une tâche comme réalisée directement
- [ ] Les tâches en retard sont mises en évidence

---

## **Recherche et Filtres**

### **US018 - Recherche globale**
**En tant qu'** utilisateur  
**Je veux** rechercher rapidement un contact, prospect ou client  
**Afin de** accéder directement à l'information recherchée  

**Critères d'acceptation :**
- [ ] Je peux saisir un nom, entreprise ou email
- [ ] La recherche fonctionne en temps réel (autocomplétion)
- [ ] Les résultats affichent le nom, entreprise et statut
- [ ] Je peux cliquer sur un résultat pour accéder à la fiche

### **US019 - Filtres avancés**
**En tant qu'** utilisateur  
**Je veux** filtrer mes contacts selon plusieurs critères  
**Afin de** cibler des segments spécifiques  

**Critères d'acceptation :**
- [ ] Je peux filtrer par statut (contact/prospect/client)
- [ ] Je peux filtrer par source d'acquisition
- [ ] Je peux filtrer par période de création
- [ ] Je peux filtrer par niveau d'intérêt (pour les prospects)
- [ ] Les filtres sont combinables
- [ ] Je peux sauvegarder mes filtres favoris

---

## **User Stories Techniques**

### **US020 - Performance et rapidité**
**En tant qu'** utilisateur  
**Je veux** que l'application soit rapide  
**Afin de** être efficace dans mon travail quotidien  

**Critères d'acceptation :**
- [ ] Les pages se chargent en moins de 2 secondes
- [ ] La recherche affiche les résultats instantanément
- [ ] Les formulaires se soumettent rapidement
- [ ] L'application fonctionne sur mobile et tablette

### **US021 - Sauvegarde automatique**
**En tant qu'** utilisateur  
**Je veux** que mes données soient sauvegardées automatiquement  
**Afin de** ne jamais perdre mon travail  

**Critères d'acceptation :**
- [ ] Les formulaires se sauvegardent automatiquement
- [ ] Un indicateur montre l'état de sauvegarde
- [ ] En cas d'erreur, je suis informé immédiatement
- [ ] Mes données sont récupérables même après fermeture accidentelle

---

## **Priorités de développement**

### **Sprint 1 - Fondations (MVP)**
**Objectif :** Base fonctionnelle du CRM avec gestion des contacts
- US001 - Connexion utilisateur
- US002 - Ajouter un contact
- US003 - Consulter la liste des contacts
- US004 - Modifier un contact
- US005 - Supprimer un contact
- US016 - Visualiser les statistiques (basique)
- US018 - Recherche globale
- US020 - Performance et rapidité

### **Sprint 2 - Cycle commercial**
**Objectif :** Gestion complète du cycle prospect → client
- US006 - Convertir un contact en prospect
- US007 - Suivre l'évolution d'un prospect
- US008 - Convertir un prospect en client
- US009 - Consulter la liste des clients
- US010 - Mettre à jour un client
- US011 - Planifier une action
- US012 - Marquer une action comme réalisée
- US017 - Voir mes tâches du jour

### **Sprint 3 - Finalisation et optimisation**
**Objectif :** Fonctionnalités avancées et expérience utilisateur
- US013 - Consulter l'historique des actions
- US014 - Uploader un document
- US015 - Consulter les documents
- US019 - Filtres avancés
- US021 - Sauvegarde automatique