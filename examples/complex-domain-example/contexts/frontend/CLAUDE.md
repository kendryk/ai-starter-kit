# Contexte Frontend — Projet modulaire

Surcharge du contexte frontend générique pour une application structurée
en modules avec séparation claire des responsabilités.

---

## Stack (exemple)

- framework frontend (ex : Angular, React, Vue…)
- langage (TypeScript recommandé)
- gestion des états / flux (ex : RxJS, store…)
- librairie UI (optionnelle)
- outils de build adaptés

---

## Structure du frontend (exemple)

```text
app/
├── core/        # Services globaux (auth, config, API…)
├── shared/      # Composants et utilitaires réutilisables
├── features/    # Modules fonctionnels
└── models/      # Types / interfaces
```

---

## Règles d’organisation

- les modules fonctionnels sont isolés
- les éléments communs sont centralisés dans `shared`
- les services globaux sont dans `core`
- éviter les dépendances directes entre modules

---

## Conventions

### Services

- centraliser les appels API dans des services dédiés
- éviter les appels réseau dans les composants
- privilégier des services réutilisables

---

### Composants

- garder les composants simples et lisibles
- limiter la logique métier dans les composants
- déléguer la logique aux services

---

### Gestion des flux

- éviter les appels imbriqués (callback / subscribe)
- privilégier les patterns réactifs ou déclaratifs
- gérer correctement les abonnements (unsubscribe, lifecycle)

---

###  UI

- utiliser une librairie UI cohérente si nécessaire
- privilégier la cohérence visuelle à la surpersonnalisation

---

## Typage

- éviter `any`
- typer explicitement les données
- aligner les modèles frontend avec les DTO backend

---

##  Bonnes pratiques

- séparation claire des responsabilités
- composants réutilisables
- code lisible et maintenable
- gestion propre des dépendances

---

##  À éviter

- dépendances circulaires entre modules
- logique métier dans les templates
- composants trop volumineux
- duplication de logique
- couplage fort entre modules

