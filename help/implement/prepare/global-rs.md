---
title: Suites de rapports globales dans Adobe Analytics
description: Découvrez les avantages et les conditions requises pour utiliser une suite de rapports globale.
translation-type: ht
source-git-commit: d7c4412feb85f4381d8811b29fc23c9c85d23555

---


# Considérations relatives aux suites de rapports globales

Une suite de rapports globale est une suite de rapports qui collecte des données de tous les domaines et applications dont votre organisation est propriétaire. Cette technique de collecte de données nécessite une préparation et peut nécessiter une coordination entre les équipes de votre entreprise.

## Avantages

Dans la plupart des cas, Adobe recommande de mettre en œuvre une suite de rapports globale.

* **Données agrégées :** les suites de rapports globales vous permettent d’afficher les IPC et les événements de succès sur les sites que vous possédez. La segmentation et les suites de rapports virtuelles peuvent être utilisées pour afficher des données spécifiques au site.
* **Prise en charge d’Analytics sur l’ensemble des appareils :** CDA nécessite une suite de rapports qui collecte des données à plusieurs endroits, comme votre site web et votre application mobile. Des appareils distincts peuvent assembler des données si leur mise en œuvre est correcte. Pour plus d’informations, reportez-vous à la section [Analytics sur l’ensemble des appareils](../../components/cda/cda-home.md) dans le guide d’utilisation Composants.
* **Pas besoin de plusieurs suites de rapports :** toutes les données peuvent être collectées dans une seule suite de rapports. Il est donc moins probable qu’un développeur envoie par erreur des données à la mauvaise suite de rapports.
* **Pas besoin de cumuls :** les cumuls sont une fonctionnalité relativement ancienne qui agrège quotidiennement les données de chaque suite de rapports. Les cumuls ne dédupliquent pas les données de visite ou de visiteur, ce qui peut entraîner une augmentation de leur nombre. Voir [Cumuls](../../admin/c-manage-report-suites/rollup-report-suite.md) dans le guide d’utilisation Administrateur pour plus d’informations.
* **Gagnez du temps :** les projets Workspace, les classifications, les segments et les mesures calculées sont liés à la même suite de rapports globale. Les administrateurs passent moins de temps à gérer ces composants et la gouvernance des données.
* **Attribution inter-marques plus précise :** si un visiteur commence sur un site, puis clique sur un autre de vos sites avant de déclencher un événement de succès, l’attribution est collectée avec précision. Par exemple, un visiteur clique sur un lien de recherche payante et accède au site A. Il clique ensuite sur un lien vers le site B, puis effectue un achat. Une suite de rapports globale attribue correctement les attributs qui rachètent à la recherche payante.
* **Mise en œuvre simplifiée :** puisque toutes les marques/tous les sites envoient des données dans la même suite de rapports, vos mises en œuvre sur chaque site sont alignées. Cette gouvernance appliquée garantit qu’une dimension ou une mesure spécifique est enregistrée dans la même eVar ou le même événement. Les administrateurs, les testeurs, les propriétaires de la gestion des balises et les analystes bénéficient de cette simplification.

> [!NOTE] La coordination d’une mise en œuvre globale d’une suite de rapports est un projet volumineux. Adobe conseille de travailler avec un consultant afin de réduire les complications et les problèmes qui surviennent.

## Démarrage d’une nouvelle mise en œuvre avec une suite de rapports globale

Suivez les instructions générales suivantes pour comprendre le processus de mise en œuvre d’une suite de rapports globale.

1. Créez la suite de rapports globale dans Adobe Analytics. Voir [Création d’une suite de rapports](../../admin/admin-console/create-report-suite.md) dans le guide d’utilisation Administrateur pour en savoir plus.
2. Travaillez avec les équipes de votre entreprise responsables de chaque domaine. De nombreuses équipes ont des exigences de rapport spécifiques à leur secteur d’activité.
3. Enregistrez et consolidez toutes ces exigences dans un [document de conception de solution](solution-design.md). Si des équipes ont des exigences similaires pour une dimension, elles peuvent utiliser la même variable personnalisée. Par exemple, si les sites A et B nécessitent tous deux une dimension de chemin de navigation, les mises en œuvre des deux sites peuvent envoyer ces données par le biais d’eVar1.
   > [!IMPORTANT] Assurez-vous que toute variable personnalisée donnée est utilisée de manière similaire dans les domaines. N’utilisez pas la même eVar ou le même événement à des fins différentes sur vos sites.
4. Assurez-vous que chaque domaine comporte une couche de données pour simplifier la collecte des données. Les données peuvent toujours être collectées sans couche de données, mais la fiabilité et la longévité de votre mise en œuvre diminuent, en particulier lors de la refonte de votre site.
5. Utilisez Adobe Experience Platform Launch pour mettre en œuvre Analytics. Les différents sites nécessiteront probablement différents éléments de données. Utilisez des règles spécifiques à chaque domaine pour vous assurer que chaque élément de données est correctement renseigné, puis affectez ces éléments de données à leurs eVars et événements respectifs. Reportez-vous à la section [Présentation de Launch](https://docs.adobe.com/content/help/fr-FR/launch/using/overview.html) dans le guide d’utilisation d’Adobe Experience Platform Launch.
6. Incluez le [service Adobe Experience Cloud ID](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html) et utilisez la fonction [appendVisitorIDsTo](https://docs.adobe.com/content/help/fr-FR/id-service/using/id-service-api/methods/appendvisitorid.html). Cette fonction fusionne les données des visiteurs lorsque les utilisateurs effectuent des clics d’un domaine à un autre.

## Modification d’une mise en œuvre existante avec une suite de rapports globale

Le processus de transfert d’une mise en œuvre existante sur plusieurs sites vers une suite de rapports globale unique nécessite plus de temps et de coordination entre les équipes de votre entreprise.

1. Déterminez si vous souhaitez utiliser l’une de vos suites de rapports existantes ou si vous souhaitez recommencer à zéro avec une nouvelle suite de rapports. Si vous souhaitez modifier les utilisations des variables existantes dans votre mise en œuvre, il est recommandé de commencer par une nouvelle suite de rapports.
2. Déterminez la date de coupure pour laquelle vous souhaitez passer à une suite de rapports globale. Le meilleur moment pour effectuer une coupure se trouve entre deux périodes de rapport importantes ou avec des modifications majeures de votre site. Par exemple, le début d’un trimestre ou d’une année fiscale, l’actualisation d’un site ou la modification d’un nouveau système de gestion des balises.
3. Suivez les étapes ci-dessus (créez une suite de rapports, rassemblez les exigences de création de rapports dans un document de conception de solution et établissez une couche de données sur chaque site). Lors de la mise en œuvre de Launch, validez votre mise en œuvre à l’aide d’une version de développement de votre site web.
4. Une fois que vous avez vérifié que votre mise en œuvre fonctionne sur le développement, mettez en œuvre votre mise en œuvre de Launch en direct à la date de coupure.

## Pages connexes

[Passage du balisage multisuite à une suite de rapports globale et à des suites de rapports virtuelles](../../components/vrs/vrs-considerations.md)
[Comparaison des cumuls et des suites de rapports globales](../../admin/c-manage-report-suites/rollup-report-suite.md)
