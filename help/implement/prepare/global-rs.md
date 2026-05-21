---
title: Suites de rapports globales dans Adobe Analytics
description: Découvrez les avantages et les conditions requises pour utiliser une suite de rapports globale.
feature: Implementation Basics
exl-id: fa949b1e-80bd-41cf-a294-c840503b568f
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/Y96K5iwjDCqXBzMeYVGJA06e115acL3aZOJl8oCBBEs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b0ca67c6-0a35-482c-ad91-baac1bcb26d6id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c8add8f2-4250-4fd9-9cde-9707036c567did: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 878
ht-degree: 96%

---

# Considérations relatives aux suites de rapports globales

Une suite de rapports globale est une suite de rapports qui collecte des données de tous les domaines et applications dont votre organisation est propriétaire. Cette technique de collecte de données nécessite une préparation et peut nécessiter une coordination entre les équipes de votre entreprise.

## Avantages

Dans la plupart des cas, Adobe recommande de mettre en œuvre une suite de rapports globale.

* **Données agrégées :** les suites de rapports globales vous permettent d’afficher les IPC et les événements de succès sur les sites que vous possédez. La segmentation et les suites de rapports virtuelles peuvent être utilisées pour afficher des données spécifiques au site.
* **Prise en charge d’Analytics sur l’ensemble des appareils :** Analytics sur l’ensemble des appareils nécessite une suite de rapports qui collecte des données à plusieurs endroits, comme votre site web et votre application mobile. Des appareils distincts peuvent assembler des données si leur mise en œuvre est correcte. Pour plus d’informations, reportez-vous à la section [Analytics sur l’ensemble des appareils](../../components/cda/overview.md) dans le guide d’utilisation des composants.
* **Pas besoin de plusieurs suites de rapports :** toutes les données peuvent être collectées dans une seule suite de rapports. Il est donc moins probable qu’un développeur envoie par erreur des données à la mauvaise suite de rapports.
* **Pas besoin de cumuls :** les cumuls sont une fonctionnalité relativement ancienne qui agrège quotidiennement les données de chaque suite de rapports. Les cumuls ne dédupliquent pas les données de visite ou de visiteur, ce qui peut entraîner une augmentation de leur nombre. Voir [Cumuls](../../admin/tools/manage-rs/rollup-report-suite.md) dans le guide d’utilisation destiné à l’administrateur pour plus d’informations.
* **Gagnez du temps :** les projets Workspace, les classifications, les segments et les mesures calculées sont liés à la même suite de rapports globale. Les administrateurs passent moins de temps à gérer ces composants et la gouvernance des données.
* **Attribution inter-marques plus précise :** si un visiteur commence sur un site, puis clique sur un autre de vos sites avant de déclencher un événement de succès, l’attribution est collectée avec précision. Par exemple, un visiteur clique sur un lien de recherche payante et accède au site A. Il clique ensuite sur un lien vers le site B, puis effectue un achat. Une suite de rapports globale réattribue correctement cet achat au référencement payant.
* **Mise en œuvre simplifiée :** puisque toutes les marques/tous les sites envoient des données dans la même suite de rapports, vos mises en œuvre sur chaque site sont alignées. Cette gouvernance appliquée garantit qu’une dimension ou une mesure spécifique est enregistrée dans la même eVar ou le même événement. Les administrateurs, les testeurs, les propriétaires de la gestion des balises et les analystes bénéficient de cette simplification.

>[!NOTE]
>
>La coordination d’une mise en œuvre globale d’une suite de rapports est un projet volumineux. Adobe conseille de travailler avec un consultant afin de réduire les complications et les problèmes qui surviennent.

## Démarrage d’une nouvelle mise en œuvre avec une suite de rapports globale

Suivez les instructions générales suivantes pour comprendre le processus de mise en œuvre d’une suite de rapports globale.

1. Créez la suite de rapports globale dans Adobe Analytics. Voir [Création d’une suite de rapports](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md) dans le guide d’utilisation destiné à l’administrateur pour en savoir plus.
1. Travaillez avec les équipes de votre entreprise responsables de chaque domaine. De nombreuses équipes ont des exigences de rapport spécifiques à leur secteur d’activité.
1. Enregistrez et consolidez toutes ces exigences dans un [document de conception de solution](solution-design.md). Si des équipes ont des exigences similaires pour une dimension, elles peuvent utiliser la même variable personnalisée. Par exemple, si les sites A et B nécessitent tous deux une dimension de chemin de navigation, les mises en œuvre des deux sites peuvent envoyer ces données par le biais d’eVar1.

   >[!IMPORTANT]
   >
   >Assurez-vous que toute variable personnalisée donnée est utilisée de manière similaire dans les domaines. N’utilisez pas la même eVar ou le même événement à des fins différentes sur vos sites.
1. Assurez-vous que chaque domaine comporte une couche de données pour simplifier la collecte des données. Les données peuvent toujours être collectées sans couche de données, mais la fiabilité et la longévité de votre mise en œuvre diminuent, en particulier lors de la refonte de votre site.
1. Utilisez des balises dans Adobe Experience Platform pour implémenter Analytics. Les différents sites nécessiteront probablement différents éléments de données. Utilisez des règles spécifiques à chaque domaine pour vous assurer que chaque élément de données est correctement renseigné, puis affectez ces éléments de données à leurs eVars et événements respectifs. Reportez-vous à la [présentation des balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr).
1. Incluez le service [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) et utilisez la fonction [`appendVisitorIDsTo`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/appendvisitorid.html?lang=fr). Cette fonction fusionne les données des visiteurs et visiteuses lorsque les utilisateurs et utilisatrices passent d’un domaine à un autre en cliquant sur un lien.

## Modification d’une mise en œuvre existante avec une suite de rapports globale

Le processus de transfert d’une mise en œuvre existante sur plusieurs sites vers une suite de rapports globale unique nécessite plus de temps et de coordination entre les équipes de votre entreprise.

1. Déterminez si vous souhaitez utiliser l’une de vos suites de rapports existantes ou si vous souhaitez recommencer à zéro avec une nouvelle suite de rapports. Si vous souhaitez modifier les utilisations des variables existantes dans votre mise en œuvre, il est recommandé de commencer par une nouvelle suite de rapports.
2. Déterminez la date de coupure pour laquelle vous souhaitez passer à une suite de rapports globale. Le meilleur moment pour effectuer une coupure se trouve entre deux périodes de rapport importantes ou avec des modifications majeures de votre site. Par exemple, le début d’un trimestre ou d’une année fiscale, l’actualisation d’un site ou la modification d’un nouveau système de gestion des balises.
3. Suivez les étapes ci-dessus (créez une suite de rapports, rassemblez les exigences de création de rapports dans un document de conception de solution et établissez une couche de données sur chaque site). Lors de l’implémentation de balises dans Adobe Experience Platform, validez votre implémentation à l’aide d’une version de développement de votre site web.
4. Une fois que vous avez confirmé que votre implémentation fonctionne en développement, poussez votre implémentation de balises en direct à la date de basculement.

>[!MORELIKETHIS]
>
>[Balisage multisuite remplacé par une suite de rapports globale et des suites de rapports virtuelles](../../components/vrs/vrs-considerations.md)
>[Comparaison des cumuls et des suites de rapports globales](../../admin/tools/manage-rs/rollup-report-suite.md)
