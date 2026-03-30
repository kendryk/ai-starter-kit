# Prompt : Ajouter une permission métier

## Quand l'utiliser

Quand on crée un nouvel endpoint ou une nouvelle fonctionnalité nécessitant un contrôle d'accès.

## Agent recommandé

`expert-securite` avec contexte `backend`

## Prompt à copier

> Je dois ajouter une permission pour la fonctionnalité **[NOM_FONCTION]**.
>
> Contexte :
> - Module backend concerné : [NOM_MODULE]
> - Type d'accès : [consultation / modification / les deux]
> - Endpoint(s) REST à sécuriser : [LISTE DES ENDPOINTS]
> - Profils qui doivent avoir cette permission : [LISTE DES PROFILS]
>
> Génère :
> 1. Le nom exact de la permission (format `APP_{nom}_{action}`)
> 2. La migration Flyway pour l'INSERT dans `conf_permission`
> 3. L'annotation `@PreAuthorize` sur le(s) controller(s)
> 4. Les instructions de synchronisation Keycloak

## Informations à préparer avant

- Nom de la fonction métier (en français, sera converti en snake_case)
- Type d'action (consult, modif)
- Endpoints concernés
- Profils utilisateurs ciblés
