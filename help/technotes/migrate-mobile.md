---
description: Découvrez comment migrer les règles de traitement Mobile Services vers Adobe Analytics
title: Migration des règles de traitement Mobile Services vers Adobe Analytics
translation-type: tm+mt
source-git-commit: bdb6f9ba435513cd1dc3febf35eae0e821c756ca
workflow-type: tm+mt
source-wordcount: '680'
ht-degree: 18%

---


# Migration des règles de traitement Mobile Services vers Adobe Analytics

Avec le prochain crépuscule (non encore annoncé) de la fonctionnalité Adobe Mobile Services, ce document vous fournit des instructions sur la migration des règles de traitement supplémentaires - au-delà des mesures de cycle de vie - que vous avez créées dans l’interface utilisateur Mobile Services vers Adobe Analytics.

Les règles de traitement servent à déplacer des valeurs des variables Données contextuelles vers des props et des eVars. Par exemple, vous pouvez placer la valeur d’une variable de données contextuelles de &quot;terme de recherche&quot; dans la valeur d’un eVar de variable Commerce et remplacer cette valeur sur chaque accès. Sans règles de traitement, les variables de données contextuelles n’ont aucun sens et ne renseignent des données dans aucun rapport dans Analytics.

## Migrer les règles de traitement

Si vous exploitez Mobile Services pour des fonctionnalités complémentaires telles que les règles de traitement et les fonctions de rapports d’utilisation, vous pouvez passer facilement à l’interface utilisateur d’Analytics (interface utilisateur des règles de traitement ou Analysis Workspace) pour accomplir ces fonctions. Pour les mesures de cycle de vie ou les règles configurées dans l’interface utilisateur des règles de traitement AA, il n’est pas nécessaire d’effectuer une migration. Les mesures de cycle de vie sont des mesures prêtes à l’emploi qui sont automatiquement collectées lors de la première mise en oeuvre du kit SDK Mobile dans votre application.

Cependant, si vous configurez d’autres règles de traitement dans l’interface utilisateur de Mobile Services (au-delà des mesures de cycle de vie), vous devez les migrer afin de pouvoir les modifier ou les supprimer dans Analytics après avoir perdu l’accès à Mobile Services.

1. Connectez-vous à experience.adobe.com et accédez à Mobile Services.
1. Cliquez sur l’icône d’engrenage d’une application mobile dont vous souhaitez migrer les mappages de variables contextuelles vers Adobe Analytics.
1. Cliquez sur l’option de menu **[!UICONTROL Gérer les variables et mesures]** , puis sur l’onglet Variables **** personnalisées. Ici, vous pouvez voir quels mappages de variables contextuelles (données contextuelles) ont été ajoutés à la configuration. Notez ces configurations (ou prenez une capture d’écran). Exemple :

   ![Variable de contexte](assets/context-var.png)

1. Dans l’Experience Cloud, passez à Adobe Analytics et vérifiez que vous êtes dans la même suite de rapports mobile que celle que vous recherchiez dans Mobile Services.
1. Sélectionnez Admin > Report Suites > Modifier les paramètres > Général > Règles de traitement.
1. Cliquez sur Ajouter une règle.
1. Ignorez les conditions et continuez à ajouter les mêmes variables contextuelles qui existent/s dans Mobile Services.

   ![Règle de traitement](assets/proc-rule.png)

## Rapports d&#39;utilisation mobile en Analysis Workspace

Outre les mesures et dimensions mobiles (si la suite de rapports est activée pour Mobile Services), Analysis Workspace contient plusieurs modèles de projet Mobile qui peuvent faciliter l’analyse :

* Message : est axé sur les performances de la messagerie in-app et push.
* Emplacement : comprend une carte représentant les données de positionnement.
* Mesures clés : sachez de quelle façon se comportent les mesures clés de votre application.
* Utilisation de l’application : combien d’utilisateurs, de lancements et de premiers lancements de l’application avait l’application et quelle est la durée de session moyenne ?
* Acquisition : Quel est l’impact des liens d’acquisition mobile ?
* Performances : quelles sont les performances de l’application et où les utilisateurs rencontrent-ils des problèmes ?
* Rétention : qui sont mes fidèles utilisateurs et que font-ils ?
* Parcours : quels sont les schémas d’utilisation dominants de mon application ?

Voici un extrait du modèle d’utilisation des applications mobiles :

![Utilisation des applications mobiles](assets/mobile-app-usage.png)

Pour accéder aux modèles :

1. Connectez-vous à experience.adobe.com et sélectionnez Analytics.
1. Assurez-vous d’être dans une suite de rapports activée pour Mobile Services.
1. Cliquez sur l’onglet Espace de travail.
1. Cliquez sur Créer un projet.
1. Sélectionnez l’un des modèles Mobile, puis cliquez sur Créer.

## Migration d’autres fonctionnalités Mobile Services

La fonctionnalité Mobile Services suivante est également liée à Adobe Analytics, mais requiert un SKU Adobe Analytics acheté :

* Liens d’acquisition
* Messagerie Push
* Messagerie in-app
* Gestion des points d&#39;intérêt d&#39;emplacement

Si vous utilisez Mobile Services pour les fonctionnalités payantes, vous n’avez pas de chemin de migration viable vers d’autres outils internes/externes :

* Pour les liens d’acquisition, nous pouvons vous diriger vers des partenaires d’Adobe pour répondre à vos besoins.
* Bien que les versions des messages Push et des messages In-App soient disponibles dans Adobe Campaign Standard et Adobe Campaign Classic (push uniquement), l’ensemble de données sous-jacentes utilisé pour le ciblage est différent et aucune migration des activités de données ou de messagerie n’est possible.
* Pour la fonctionnalité Emplacement, nous vous encourageons à adopter le nouveau service [Emplacement](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, gratuit pour tous les clients AEP.
