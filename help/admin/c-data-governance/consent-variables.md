---
description: Variables de gestion du consentement dans la confidentialité des données.
seo-description: Variables de gestion du consentement dans la confidentialité des données.
seo-title: Variables de gestion du contenu
solution: Analytics
title: Variables de gestion du contenu
topic: Outils d’administration
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# Variables de gestion du contenu

Pour faciliter la gestion des données de confidentialité, un ensemble de variables réservées peut être utilisé conjointement avec des variables de données contextuelles spécifiques.
Ces variables de gestion du consentement fournissent une structure facile à utiliser pour capturer l’état du consentement sur chaque accès Analytics.

## Variables

* Droit d’opposition de gestion du consentement
   * Variable réservée : Prop de liste
   * Type : Chaîne délimitée par des virgules
   * Contient:
      * `contextData.['cm.ssf']=1` affiché en tant que SSF
      * `contextData.['opt.dmp']=N` affiché en tant que DMP
      * `contextData.['opt.sell']=N` affiché comme VENTE

* Accord préalable de gestion du consentement
   * Variable réservée : Prop de liste
   * Type : Chaîne délimitée par des virgules
   * Contient:
      * `contextData.['opt.dmp']=Y` affiché en tant que DMP
      * `contextData.['opt.sell']=Y` affiché comme VENTE

## Création de rapports  

Les variables de gestion du consentement peuvent être activées via un nouveau paramètre de confidentialité disponible dans la console d’administration Analytics.

Chaque suite de rapports peut être configurée pour :
1. Dans Rapports et analyses, cliquez sur Admin &gt; Report Suites.
1. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings &gt; Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. Cliquez sur le bouton [!UICONTROL Activer les rapports] de confidentialité des données.  Remarque : une fois activées, ces variables ne peut pas être désactivées.

   ![](assets/rsm-privacy-enable.png)

1. Une fois activé, un message de confirmation s’affiche.

   ![](assets/rsm-privacy-config.png)

1. Les variables réservées sont désormais disponibles pour la création de rapports.  Voir Exclusion de la gestion du consentement et Exclusion de la gestion du consentement.

   ![](assets/rsm-privacy-reports.png)

## Mise en œuvre

Trois variables de données contextuelles ont été prédéfinies pour fonctionner avec les variables réservées de la gestion du consentement.  Il appartient à chaque ingénieur de l’implémentation de déterminer comment gérer et conserver le paramètre de ces variables.

Voir Variables [de données](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) contextuelles pour obtenir des instructions générales sur l’implémentation des variables de données contextuelles.

### SSF

* Données contextuelles: `contextData.['cm.ssf']`
* Valeurs acceptées :
   * `1` - Lors de l'envoi de la valeur `1`, cela indique que le transfert côté serveur est dans un état d'exclusion. La valeur `1` associée à cette variable bloquera le partage de cet accès avec Adobe Audience Manager. Voir Conformité [AAM à la confidentialité en ligne.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * Aucune autre valeur n’est acceptée pour ce paramètre

### DMP

* Données contextuelles: `contextData.['opt.dmp']`
* Valeurs acceptées :
   * `N` - Lors de l'envoi de la valeur `N`, cela indique que le consommateur choisit de ne pas partager sur les plateformes de gestion de données. Notez que ce n’est pas le cas actuellement du partage de blocs avec AAM.  Utilisez SSF pour cette fonctionnalité.
   * `Y` - Lors de l'envoi de la valeur `Y`, cela indique que le consommateur opte pour le partage sur les plateformes de gestion de données.

### VENDRE

* Données contextuelles: `contextData.['opt.sell']`
* Valeurs acceptées :
   * `N` - Lors de l'envoi de la valeur `N`, cela indique que le consommateur choisit de ne pas partager ou vendre les données à des tiers.
   * `Y` - Lorsque vous envoyez la valeur `Y`, cela indique que le consommateur choisit de partager ou de vendre les données à des tiers.
