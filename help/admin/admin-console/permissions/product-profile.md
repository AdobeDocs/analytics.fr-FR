---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Profils de produit dans Adobe Analytics

Les profils de produit sont un paramètre prédéfini d'autorisation que peuvent affecter les administrateurs de produits aux utilisateurs d'une organisation. Si vous créez un profil de produit et affectez un utilisateur Experience Cloud à ce profil, il hérite des éléments d'autorisation contenus dans le profil du produit.

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## Administrateurs du profil du produit

Les administrateurs de profil de produit sont un groupe facultatif qui peut ajouter ou supprimer des utilisateurs à ce profil de produit. Notez qu'un administrateur du profil de produit n'est pas identique à un administrateur du produit :

* Les administrateurs du profil de produit sont simplement responsables de la liste des utilisateurs d'un profil de produit.
* Les administrateurs du profil de produit n'ont pas accès entièrement à Adobe Analytics. L'accès complet à Adobe Analytics est réservé aux administrateurs de produits.
* Les administrateurs de profil de produit ne peuvent pas ajuster les éléments d'autorisations dans leur profil de produit ; un administrateur du produit doit effectuer les ajustements des articles d'autorisation.
* Les administrateurs de profils de produits sont idéaux pour les prospects d'équipe ou les gestionnaires qui doivent simplement accorder et gérer l'accès à Adobe Analytics pour leur équipe. Il n'est pas nécessaire de toucher les administrateurs système ou les administrateurs de produits pour accorder l'accès à Adobe Analytics.

## Articles d'autorisation Adobe Analytics

Les autorisations minimales requises dans un profil de produit pour accéder à Adobe Analytics sont les suivantes :

* Le profil du produit doit avoir accès à au moins une suite de rapports.
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### Suites de rapports

Accorde l'accès aux suites de rapports qui appartiennent à votre organisation Analytics. Un utilisateur doit appartenir à au moins une suite de rapports pour pouvoir accéder à Adobe Analytics.

### Mesures

Accorde l'accès aux mesures dans votre suite de rapports. Les mesures sont répertoriées comme leur composant respectif dans Analysis Workspace ou si la mesure est disponible dans les rapports et analyses, disponible sous la forme d'un élément de menu sous Mesures du site.

Les mesures personnalisées sont intitulées Evénement personnalisé 1-1000 pour les garder indépendantes des suites de rapports. Si « Event 1 personnalisée » est un élément d'autorisation activé, cet utilisateur a accès à event 1 dans toutes les suites de rapports du profil du produit.

### Dimensions

Accorde l'accès aux dimensions dans votre suite de rapports. Les dimensions sont répertoriées comme leur composant respectif dans Analysis Workspace, ou si la dimension est disponible dans les rapports et analyses, disponible sous forme d'élément de menu.

Les variables personnalisées, telles que evars, sont étiquetées « Conversion personnalisée 1-250 » pour les garder indépendantes des suites de rapports. Si « Conversion personnalisée 1 » est un élément d'autorisation activé, cet utilisateur a accès à evar 1 dans toutes les suites de rapports du profil du produit.

### Outils de suites de rapports

Les éléments d'autorisation des outils de suite de rapports donnent accès aux fonctionnalités propres aux suites de rapports auxquelles l'utilisateur a accès. See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Outils Analytics

Les éléments d'autorisation des outils Analytics donnent accès aux fonctionnalités qui dépendent des paramètres de la suite de rapports. See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## Développeurs de profils de produits

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
