# Prompt : Créer une librairie frontend

## Quand l'utiliser

Quand on démarre un nouveau module frontend (librairie Angular).

## Agent recommandé

`assistant-dev` avec contexte `frontend`

## Prompt à copier

> Je dois créer une nouvelle librairie frontend pour le module **[NOM_MODULE]**.
>
> Contexte :
> - Ce module affiche [DESCRIPTION DES ÉCRANS PRINCIPAUX]
> - Il consomme les endpoints REST de [NOM_MODULE_BACKEND]
> - Il a besoin d'accéder aux types de [AUTRES_TYPES_LIBS]
>
> Génère :
> 1. La structure de la librairie `[nom]-ihm-lib` (module, composants, services)
> 2. La librairie de types `[nom]-types-ihm-lib` (interfaces et enums)
> 3. Le `ng-package.json` de chaque librairie
> 4. Le NgModule principal avec les imports nécessaires
> 5. Un composant exemple (liste + formulaire) avec Angular Material
> 6. Un service HTTP pour les appels API principaux
> 7. Les mises à jour à faire dans `module-ihm-app` pour l'import

## Informations à préparer avant

- Nom du module métier
- Écrans principaux (liste, détail, formulaire, etc.)
- Endpoints REST consommés
- Permissions à vérifier côté frontend (si applicable)
- Librairies de types à importer

