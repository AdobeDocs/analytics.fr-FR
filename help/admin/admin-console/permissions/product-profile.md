---
source-git-commit: 03b1195225b97f3ea151eb5b4f39fbed746b3654
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '646'
ht-degree: 100%

---
# Profils de produit pour Adobe Analytics

Les profils de produit sont des paramètres dʼautorisation prédéfinis que les administrateurs des produits peuvent attribuer aux utilisateurs dʼune organisation. Si vous créez un profil de produit et que vous lui affectez un utilisateur Experience Cloud, il hérite des éléments d’autorisation contenus dans le profil de produit.

Voir [Gestion des produits et des profils](https://helpx.adobe.com/fr/enterprise/using/manage-products-and-profiles.html) dans le guide de l’utilisateur Enterprise pour obtenir des informations générales sur les profils de produit.

## Administrateurs de profil de produit

Les administrateurs de profil de produit sont un groupe facultatif qui peut ajouter des utilisateurs à ce profil de produit ou en supprimer. Notez qu’un administrateur de profil de produit n’est pas identique à un administrateur de produit :

* Les administrateurs de profil de produit ne disposent pas d’un accès complet à Adobe Analytics. L’accès complet à Adobe Analytics est réservé aux administrateurs de produit.
* Les administrateurs des profils de produit peuvent ajuster les éléments dʼautorisation dans leur profil de produit.
* Les administrateurs des profils de produit peuvent affecter des profils de produit à des groupes d’utilisateurs ou en supprimer.
* Les administrateurs des profils de produit sont parfaits pour les chefs dʼéquipe ou les managers qui doivent octroyer et gérer lʼaccès à Adobe Analytics pour leur équipe. Les utilisateurs n’ont pas besoin d’intervenir auprès des administrateurs système ou des administrateurs de produit pour octroyer l’accès à Adobe Analytics.

## Éléments d’autorisation Adobe Analytics

Les autorisations minimales requises dans un profil de produit pour accéder à Adobe Analytics sont les suivantes :

* Le profil de produit doit avoir accès à au moins une suite de rapports.
* Le profil de produit doit appartenir à l’élément d’autorisation lié aux outils Analytics **Accès à Analysis Workspace** (ou **Accès aux Reports &amp; Analytics**).

### Suites de rapports

Accorde l’accès aux suites de rapports qui appartiennent à votre organisation Analytics. Un utilisateur doit appartenir à au moins une suite de rapports pour recevoir un accès à Adobe Analytics.

### Mesures

Accorde l’accès aux mesures de votre suite de rapports. Les mesures sont répertoriées comme leur composant respectif dans Analysis Workspace ou, si la mesure est disponible dans Reports &amp; Analytics, sont disponibles en tant qu’élément de menu sous Mesures du site.

Les mesures personnalisées sont étiquetées « Événements personnalisés 1-1 000 » afin de rester indépendantes des suites de rapports. Si « Événement personnalisé 1 » est un élément d’autorisation activé, cet utilisateur a accès à événement1 dans toutes les suites de rapports du profil de produit.

### Dimensions

Accorde l’accès aux dimensions de votre suite de rapports. Les dimensions sont répertoriées en tant que composant respectif dans Analysis Workspace, ou si la dimension est disponible dans Reports &amp; Analytics, sont disponibles en tant qu’élément de menu.

Les variables personnalisées, telles que les eVars, sont étiquetées « Conversions personnalisées 1-250 » afin de rester indépendantes des suites de rapports. Si « Conversion personnalisée 1 » est un élément d’autorisation activé, cet utilisateur a accès à eVar1 dans toutes les suites de rapports du profil de produit.

### Outils de suites de rapports

Les éléments d’autorisation liés aux outils de suites de rapports octroient l’accès aux fonctionnalités spécifiques aux suites de rapports auxquelles l’utilisateur a accès. Pour obtenir la liste complète des descriptions et des éléments d’autorisation, reportez-vous à la section [Outils de suite de rapports](report-suite-tools.md).

### Outils Analytics

Les éléments d’autorisation liés aux outils Analytics octroient l’accès à des fonctionnalités indépendantes des paramètres de suite de rapports. Reportez-vous aux [Autorisations du profil de produit pour les outils Analytics](analytics-tools.md) afin dʼobtenir la liste complète des éléments et des descriptions dʼautorisation.

## Développeurs de profil de produit

Les développeurs sont similaires aux utilisateurs, sauf qu’ils peuvent utiliser l’API Experience Cloud sur Adobe I/O. Pour plus d’informations, voir [Gestion des développeurs](https://helpx.adobe.com/fr/enterprise/using/manage-developers.html) dans le guide de l’utilisateur Enterprise. Si un utilisateur bénéficie dʼun accès Développeur pour nʼimporte quel profil, il peut accéder à la console Développeur (console.adobe.io) et modifier les intégrations dʼAdobe Analytics. Les appels et les réponses de lʼAPI Analytics autorisés pour lʼutilisateur dépendront des autorisations de tous les profils dans lesquels cet utilisateur a un accès Développeur.

Par exemple, avec les autorisations du profil comprenant toutes les mesures, toutes les dimensions et une suite de rapports, un membre du profil avec un accès Développeur pourrait effectuer des appels API pertinents à tout composant de la suite concernée. Avec lʼajout de la détection des anomalies, les rapports pourraient inclure des réponses plus complètes, comprenant les données sur les anomalies. En règle générale, si un profil accorde lʼaccès à un scénario dans lʼinterface Adobe Analytics, lʼaccès Développeur à un autre profil défini de manière similaire active les appels et réponses de lʼAPI correspondante.
