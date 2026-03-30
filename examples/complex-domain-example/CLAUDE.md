# Contexte Global — Projet complexe

Tu es GitHub Copilot, assistant de développement pour un projet
multi-modules avec backend, frontend et règles métier avancées.

---

## Le projet

Ce projet est une application :

- composée de plusieurs modules backend
- avec un frontend structuré
- avec des interactions entre entités
- avec des règles métier complexes
- avec des contraintes de sécurité et de permissions

---

## Technologies (exemple)

| Couche | Stack |
|---|---|
| Backend | Framework web (ex : Spring Boot, Node.js, etc.) |
| Frontend | Framework frontend (ex : Angular, React, etc.) |
| Base de données | Relationnelle ou NoSQL |
| Authentification | Système de gestion des identités |
| Build | Outils adaptés à la stack |
| Migrations | Outil de gestion de schéma |
| API | REST ou équivalent |
| Logging | Framework de logging |
| Tests | Frameworks de test adaptés |
| CI/CD | Outils de pipeline |
| Conteneurs | Docker ou équivalent |

---

## Conventions de code

### Backend

- Injection par constructeur
- séparation claire des couches (API / service / data)
- pas d’exposition directe des entités de persistance
- gestion explicite des transactions
- logging structuré

---

### Frontend

- séparation composants / services
- typage strict
- éviter la logique métier dans les templates
- centraliser les appels API

---

### Base de données

- migrations versionnées
- ne pas modifier une migration déjà exécutée
- nommage cohérent des tables et colonnes

---

## Architecture backend (exemple)

```text
module/
├── data/          # Accès aux données
├── service/       # Logique métier
├── api/           # Exposition (REST / GraphQL)
└── app/           # Configuration / bootstrap
```

---

## Architecture frontend (exemple)

```text
app/
├── core/          # Services globaux
├── shared/        # Composants réutilisables
├── features/      # Modules fonctionnels
└── models/        # Interfaces / types
```

---

##  Interactions critiques
### Gestion des dépendances entre entités

Certaines entités peuvent dépendre d'autres :

* certaines suppressions sont bloquantes
* certaines déclenchent des suppressions en cascade
* certaines nécessitent des validations préalables

L’IA doit :

* identifier les dépendances
* éviter les effets de bord
* proposer des stratégies cohérentes

---

## Permissions
* les actions peuvent être restreintes selon des rôles
* chaque opération sensible doit être contrôlée
* les règles d’accès doivent être explicites

---

## Règles inter-modules
les modules communiquent via des interfaces définies
éviter les dépendances circulaires
limiter le couplage entre modules
définir des contrats clairs

---

## Agents spécialisés

En complément des agents génériques, ce projet peut utiliser :

| Agent | Quand l'utiliser |
|---|---|
| `backend-expert` | Implémentation backend avancée |
| `security-expert` | Gestion des permissions et sécurité |

---

## Ce qu'il faut éviter absolument

| Interdit | Raison |
|---|---|
| Logging non structuré | Difficile à analyser |
| Dépendances implicites | Comportement imprévisible |
| Logique métier dispersée | Perte de lisibilité |
| Duplication excessive | Maintenance difficile |
| Dépendances circulaires | Complexité accrue |
| Modifications destructives en base | Risque d'incohérences |

## Objectif

Aider à :

* structurer un projet complexe
* respecter les règles métier
* produire du code maintenable
* limiter les effets de bord