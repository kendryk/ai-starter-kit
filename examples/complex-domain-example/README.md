# Exemple — Système métier complexe

Cet exemple montre comment personnaliser le template `ai-project-template`
pour un projet avec :

- backend + frontend
- règles métier complexes
- gestion des dépendances entre entités
- sécurité et permissions
- synchronisation de données entre modules

---

## Ce que contient cet exemple

```text
examples/complex-domain-system/
├── CLAUDE.md                          # Règles globales adaptées au projet
├── contexts/
│   ├── domain/CLAUDE.md               # Glossaire et règles métier
│   ├── backend/CLAUDE.md              # Conventions backend
│   └── frontend/CLAUDE.md             # Conventions frontend
├── agents/
│   ├── backend-expert.agent.md        # Patterns backend avancés
│   └── security-expert.agent.md       # Gestion des permissions
└── prompts/
    ├── add-permission-system.md       # Ajouter un système de permissions
    ├── create-frontend-module.md      # Créer un module frontend
    └── implement-data-sync.md         # Synchronisation entre modules
```

## Objectif de cet exemple

Illustrer comment adapter le template à un projet :

* avec plusieurs couches (backend / frontend)
* avec des règles métier non triviales
* avec des dépendances entre entités
* avec des contraintes de sécurité

## Comment utiliser cet exemple

1. Partir du template générique (racine du dépôt)
2. Copier le `CLAUDE.md` de cet exemple à la racine de ton projet
3. Copier les contextes dans `contexts/`
4. Copier les agents dans `.github/agents/`
5. Copier les prompts dans `docs/prompts/`
6. Adapter les fichiers à ton propre projet en respectant les conventions et patterns définis dans les contextes et agents.
   
> Cet exemple est une base d’inspiration, pas une solution prête à l’emploi.

## Stack de référence (exemple)

| Couche | Exemple de stack |
|---|---|
| Backend | Framework web ou runtime serveur (ex. : Spring Boot, NestJS, Express) |
| Frontend | Framework ou bibliothèque UI (ex. : Angular, React, Vue) |
| Base de données | SGBD relationnel ou NoSQL (ex. : PostgreSQL, MySQL, MongoDB) |
| Authentification | Solution IAM ou fournisseur d'identité (ex. : Keycloak, Auth0, Cognito) |
| Build | Outils de build et de packaging adaptés à la stack (ex. : Maven, Gradle, Vite) |
| Migrations | Outil de gestion de schéma ou de versionnement BDD (ex. : Flyway, Liquibase, Prisma) |
| Tests | Frameworks de test backend et frontend (ex. : JUnit, Vitest, Cypress) |

