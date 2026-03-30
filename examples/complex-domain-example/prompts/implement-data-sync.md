# Prompt : Gérer la suppression avec dépendances (check / delete)

##  Quand l'utiliser

Quand un module backend doit gérer la suppression d’une entité
en tenant compte des dépendances avec d’autres données.

---

##  Agent recommandé

`backend-expert` avec contexte `backend` (+ `domain` si règles métier)

---

##  Prompt à copier

> Je dois implémenter un mécanisme de vérification avant suppression
> pour le module **[NOM_MODULE]**.
>
> Contexte :
> - Entité principale : [NOM_ENTITÉ]
> - Tables impactées : [LISTE DES TABLES]
> - Relations : [DESCRIPTION DES RELATIONS]
>
> Je veux :
> 1. Une méthode de vérification (`check`) pour détecter les dépendances
> 2. Une méthode de suppression (`delete`) sécurisée
> 3. Les requêtes (JPA/SQL) pour identifier les éléments liés
> 4. Les objets de réponse (statut, messages, éléments bloquants)
> 5. Les tests unitaires associés
>
> Contraintes :
> - bloquer la suppression si dépendances critiques
> - autoriser la suppression si aucune dépendance bloquante
> - gérer les cas de suppression en cascade si nécessaire

---

## 📋 Informations à préparer

- Entité principale concernée
- Tables ou ressources dépendantes
- Type de relation (FK, association…)
- Comportement attendu :
    - blocage
    - cascade
- Messages d’erreur métier

---

## 🔄 Flux de fonctionnement (exemple)

```text
1. Le système appelle une méthode de vérification (check)
2. Le module analyse les dépendances
3. Le module retourne :
   - autorisé
   - bloqué (avec détails)
4. Si autorisé → exécution de la suppression (delete)
5. Si bloqué → retour des erreurs et arrêt du processus
```

## Points d’attention

Avant toute implémentation, vérifier :

- éviter les suppressions non contrôlées
- bien identifier toutes les dépendances
- fournir des messages clairs en cas de blocage
- garantir la cohérence des données

