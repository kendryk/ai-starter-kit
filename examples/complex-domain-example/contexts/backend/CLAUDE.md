# Contexte Backend — Projet modulaire

Surcharge du contexte backend générique pour un projet backend structuré
en modules avec séparation claire des responsabilités.

---

##  Stack (exemple)

- langage backend (ex : Java, Node.js, etc.)
- framework web (ex : Spring Boot, NestJS, etc.)
- accès aux données (ORM / repository pattern)
- outil de build
- outil de migration de schéma
- framework de logging

---

## Structure d’un module (exemple)

```text
module/
├── data/        # Accès aux données (repositories, DAO)
├── domain/      # Modèles métier (optionnel)
├── service/     # Logique métier
├── api/         # Controllers / endpoints
├── app/         # Configuration / bootstrap
└── tools/       # Scripts utilitaires
```

## Patterns recommandés

### Séparation des couches

- `api` → exposition (REST, GraphQL…)
- `service` → logique métier
- `data` → accès aux données

> Éviter le couplage direct entre ces couches.

---

### Converters / Mappers

- utiliser des objets distincts pour :
    - persistance (entities)
    - exposition (DTO)
- centraliser les transformations (mappers / converters)
- éviter la logique de mapping dispersée

---

### Injection de dépendances

- privilégier l’injection par constructeur
- éviter les injections implicites
- garder les dépendances explicites et testables

---

### Gestion des dépendances entre modules

- définir des interfaces claires entre modules
- éviter les dépendances circulaires
- limiter le couplage fort

---

## Tests

- utiliser un framework de test adapté
- mocker les dépendances externes
- suivre le pattern : Arrange / Act / Assert
- nommage recommandé : `shouldDoXWhenY`

---

## Migrations

- versionner les changements de schéma
- ne jamais modifier une migration déjà exécutée
- garder de simples scripts lisibles

---

## Logging

### Exemple

```java
private static final Logger logger = LoggerFactory.getLogger(MyService.class);
```
