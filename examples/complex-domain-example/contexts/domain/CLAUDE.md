# Contexte Métier — Système complexe

Tu es spécialisé dans un domaine métier impliquant :

- des entités interconnectées
- des règles métier complexes
- des dépendances entre objets
- des contraintes de cohérence et de sécurité

---

## Glossaire métier (exemple)

| Terme | Définition |
|---|---|
| **Entité** | Objet métier principal (ex : ressource, équipement, élément) |
| **Référentiel** | Données partagées utilisées par plusieurs modules |
| **Dépendance** | Lien entre deux entités (ex : relation, référence) |
| **Cascade** | Suppression ou modification automatique liée |
| **Blocage** | Empêche une action si certaines conditions ne sont pas remplies |
| **Événement** | Action ou changement significatif dans le système |
| **Configuration** | Paramètres définissant le comportement du système |
| **Permission** | Droit d'accès à une fonctionnalité |
| **Rôle** | Ensemble de permissions attribué à un utilisateur |
| **Portée** | Limitation des droits à un périmètre donné |

---

## 🏗Organisation du système

### Backend

Le système est structuré en modules :

- chaque module gère un périmètre fonctionnel
- les modules communiquent via des interfaces définies (API, services…)
- les données peuvent être partagées entre modules

---

### Frontend

- structuré en modules fonctionnels
- séparation entre composants, services et modèles
- mutualisation des éléments communs

---

## Interactions critiques

### Gestion des dépendances

Quand une entité est modifiée ou supprimée :

1. Le système identifie les modules concernés
2. Chaque module vérifie ses propres dépendances
3. Le système agrège les résultats :
    - autorisé
    - bloqué (avec détails)
4. Si tout est autorisé → l’opération est exécutée
5. Sinon → l’opération est annulée avec des messages explicites

---

### Gestion des permissions

- chaque action peut être restreinte
- les permissions sont associées à des rôles
- les rôles sont attribués aux utilisateurs
- les règles d’accès doivent être explicites et cohérentes

---

## Règles à respecter

- toute action critique doit vérifier les dépendances
- les suppressions doivent être contrôlées
- les règles métier doivent être explicites
- les interactions entre modules doivent être maîtrisées
- les permissions doivent être centralisées et cohérentes

---

## ⚠Points d’attention

- bien identifier toutes les dépendances
- éviter les suppressions non contrôlées
- garantir la cohérence des données
- fournir des messages clairs en cas de blocage

---

## Objectif

Aider à :

- comprendre les impacts métier
- sécuriser les opérations sensibles
- garantir la cohérence globale du système
- produire des solutions robustes et maintenables