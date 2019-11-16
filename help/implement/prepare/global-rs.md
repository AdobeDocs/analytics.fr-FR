---
title: Suites de rapports globales dans Adobe Analytics
description: Découvrez les avantages et les conditions requises pour utiliser une suite de rapports globale.
translation-type: tm+mt
source-git-commit: d7c4412feb85f4381d8811b29fc23c9c85d23555

---


# Considérations relatives aux suites de rapports globales

Une suite de rapports globale est une suite de rapports qui collecte des données de tous les domaines et applications dont votre organisation est propriétaire. Cette technique de collecte de données nécessite une préparation et peut nécessiter une coordination entre les équipes de votre entreprise.

## Avantages

Dans la plupart des cas, Adobe recommande de mettre en oeuvre une suite de rapports globale.

* **** Données agrégées : Les suites de rapports globales vous permettent d’afficher les IPC et les événements de réussite sur vos sites détenus. La segmentation et les suites de rapports virtuelles peuvent être utilisées pour afficher des données spécifiques au site.
* **** Prise en charge des analyses multipériphériques : CDA nécessite une suite de rapports qui collecte des données à plusieurs endroits, comme votre site Web et votre application mobile. Des périphériques distincts peuvent assembler des données s’ils sont implémentés correctement. Pour plus d’informations, reportez-vous à la section Analyses [](../../components/cda/cda-home.md) sur plusieurs périphériques dans le guide de l’utilisateur Composants.
* **** Pas besoin de plus d’une suite de rapports : Toutes les données peuvent être collectées dans une seule suite de rapports. Il est donc moins probable qu’un développeur envoie par erreur des données à la mauvaise suite de rapports.
* **** Pas besoin de cumuls : Les cumuls sont une fonctionnalité relativement ancienne qui agrège quotidiennement les données de chaque suite de rapports. Les cumuls ne dédupliquent pas les données de visite ou de visiteur, ce qui peut entraîner une augmentation du nombre. Voir [Cumuls](../../admin/c-manage-report-suites/rollup-report-suite.md) dans le guide de l’utilisateur Admin pour plus d’informations.
* **** Gagnez du temps : Les projets d’espace de travail, les classifications, les segments et les mesures calculées sont liés à la même suite de rapports globale. Les administrateurs passent moins de temps à gérer ces composants et la gouvernance des données.
* **** Attribution inter-marques plus précise : Si une visite commence sur un site, puis clique sur un autre de vos sites avant de déclencher un événement de réussite, l’attribution est collectée avec précision. Par exemple, un visiteur clique sur un lien de recherche payante et accède au site A. Ils cliquent ensuite sur un lien vers le site B, puis effectuent un achat. Une suite de rapports globale attribue correctement les attributs qui rachètent à la recherche payante.
* **** Mise en oeuvre simplifiée : Puisque toutes les marques/sites envoient des données dans la même suite de rapports, vos implémentations sur chaque site sont alignées. Cette gouvernance appliquée garantit qu’une dimension ou une mesure spécifique est enregistrée dans la même eVar ou le même événement. Les administrateurs, les testeurs, les propriétaires de la gestion des balises et les analystes bénéficient de cette simplification.

> [!NOTE] La coordination d’une implémentation globale d’une suite de rapports est un projet volumineux. Adobe conseille de travailler avec un consultant afin de réduire les complications et les problèmes qui surviennent.

## Démarrage d’une nouvelle implémentation avec une suite de rapports globale

Suivez les instructions générales suivantes pour comprendre le processus d’implémentation d’une suite de rapports globale.

1. Créez la suite de rapports globale dans Adobe Analytics. Voir [Création d’une suite](../../admin/admin-console/create-report-suite.md) de rapports dans le guide de l’utilisateur Admin pour en savoir plus.
2. Travaillez avec les équipes de votre entreprise responsables de chaque domaine. De nombreuses équipes ont des exigences de rapport spécifiques à leur secteur d’activité.
3. Enregistrez et consolidez toutes ces exigences dans un document [de conception de](solution-design.md)solution. Si des équipes ont des exigences similaires pour une dimension, elles peuvent utiliser la même variable personnalisée. Par exemple, si les sites A et B nécessitent tous deux une dimension de chemin de navigation, les implémentations des deux sites peuvent envoyer ces données par le biais d’eVar1.
   > [!IMPORTANT] Assurez-vous que toute variable personnalisée donnée est utilisée de manière similaire dans les domaines. N’utilisez pas la même eVar ou le même événement à des fins différentes sur vos sites.
4. Assurez-vous que chaque domaine comporte une couche de données pour simplifier la collecte des données. Les données peuvent toujours être collectées sans couche de données, mais la fiabilité et la longévité de votre implémentation diminuent, en particulier lorsque votre site est repensé.
5. Utilisez Adobe Experience Platform Launch pour implémenter Analytics. Les différents sites nécessiteront probablement différents éléments de données. Utilisez des règles spécifiques à chaque domaine pour vous assurer que chaque élément de données est correctement renseigné, puis affectez ces éléments de données à leurs eVars et événements respectifs. Reportez-vous à la section Présentation [du](https://docs.adobe.com/content/help/en/launch/using/overview.html) lancement dans le guide de l’utilisateur Lancement d’Adobe Experience Platform.
6. Incluez le service [d’ID](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Cloud et utilisez la fonction [appendVisitorIDsTo](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/appendvisitorid.html) . Cette fonction fusionne les données des visiteurs lorsque les utilisateurs cliquent d’un domaine à un autre.

## Modification d’une implémentation existante avec une suite de rapports globale

Le processus de transfert d’une implémentation existante sur plusieurs sites vers une suite de rapports globale unique nécessite plus de temps et de coordination entre les équipes de votre entreprise.

1. Déterminez si vous souhaitez utiliser l’une de vos suites de rapports existantes ou si vous souhaitez recommencer à zéro avec une nouvelle suite de rapports. Si vous souhaitez modifier les utilisations des variables existantes dans votre implémentation, il est recommandé de commencer par une nouvelle suite de rapports.
2. Déterminez la date de coupure pour laquelle vous souhaitez passer à une suite de rapports globale. Le meilleur moment pour effectuer une coupure est entre deux périodes de rapport importantes ou avec des modifications majeures de votre site. Par exemple, le début d’un trimestre ou d’une année fiscale, l’actualisation d’un site ou la modification d’un nouveau système de gestion des balises.
3. Suivez les étapes ci-dessus (créez une suite de rapports, rassemblez les exigences de création de rapports dans un document de conception de solution et établissez une couche de données sur chaque site). Lors de l’implémentation de Launch, validez votre implémentation à l’aide d’une version de développement de votre site Web.
4. Une fois que vous avez confirmé que votre mise en oeuvre fonctionne sur le développement, mettez en oeuvre votre mise en oeuvre de lancement en direct à la date de coupure.

## Pages connexes

[Passage du balisage multi-suite à une suite de rapports globale et à des suites](../../components/vrs/vrs-considerations.md)de rapports virtuelles[Comparaison des cumuls et des suites de rapports globales](../../admin/c-manage-report-suites/rollup-report-suite.md)
