---
title: Qu’est-ce que le nouveau Adobe Report Builder ?
description: Décrit la nouvelle fonctionnalité de Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 65f2f1caff36be2afc0c11297be5dd5b593e9a3d
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 29%

---

# À propos du nouveau Adobe Report Builder

Le nouveau complément de Report Builder JavaScript, initialement disponible uniquement dans Customer Journey Analytics, est désormais également introduit dans Adobe Analytics. Cette nouvelle version présente plusieurs avantages :

- Trouvez des informations dans Excel plus rapidement et plus facilement grâce à des workflows améliorés pour la création et la gestion des blocs de données, avec une plus grande flexibilité des blocs de données
- Cross-plateforme : plus de connexion à votre machine virtuelle pour utiliser Report Builder, car nous prenons désormais en charge PC, Mac et Excel Online
- Moins de temps à attendre le retour des blocs de données, grâce à la mise à niveau de l’API 2.0
- Amélioration de la vitesse.

Les utilisateurs de l’outil Report Builder hérité peuvent [convertir des classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) en nouveau Report Builder.

Report Builder vous permet de créer, modifier et actualiser facilement des rapports personnalisés à l’aide des données Adobe Analytics. Grâce à l’interface utilisateur simple et flexible de Report Builder par glisser-déposer, vous pouvez créer des requêtes de données complexes et des rapports personnalisés à partir de données Adobe Analytics, le tout dans Excel.

Avec le Report Builder, vous pouvez :

- Référencement des cellules de feuille de calcul existantes pour obtenir lʼordre de lignes, la période ou le filtre parfait
- Création de dates personnalisées à lʼaide du calendrier, des références de cellules ou des mathématiques de date
- Conception de vos tableaux et visualisations avec des outils familiers de formatage Excel

## Utilisation côte à côte du Report Builder hérité et du nouveau Report Builder

Vous pouvez toujours utiliser les deux versions de Report Builder, avec les avertissements suivants :

- N’utilisez pas les deux versions de Report Builder sur le même fichier en même temps. Ils s&#39;excluent mutuellement.
- Vous pouvez toujours utiliser le Report Builder hérité sur les classeurs hérités et le nouveau Report Builder sur les nouveaux classeurs.
- En outre, vous pouvez [convertir automatiquement les classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) au nouveau format de Report Builder. Avant cela, dupliquez et renommez le fichier .

## Fonctionnalités de Report Builder héritées non prises en charge dans le nouveau Report Builder

Lorsque vous comparez la fonctionnalité du Report Builder hérité au nouveau complément de Report Builder, certaines fonctionnalités héritées ne sont plus disponibles :

- Requêtes en temps réel

- Rapports Chemin/Abandon

- Option FTP pour les rapports planifiés

- Mesures Visiteurs. Les mesures suivantes seront toutes converties en « visiteurs uniques », même si le résultat du compte rendu des performances peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cela s’applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.

## Cas d’utilisation courants

- **Extraction de données** : Adobe Report Builder vous permet d’extraire des données d’Adobe Analytics vers Excel. Vous pouvez créer des rapports et des requêtes personnalisés pour récupérer des points de données spécifiques pertinents pour votre analyse.

- **Rapports personnalisés** : vous pouvez concevoir et formater des rapports personnalisés dans Excel en fonction de vos besoins spécifiques en matière de rapports. Cela s’avère particulièrement utile pour adapter les rapports aux différentes parties prenantes.

- **Analyse ad hoc** : les utilisateurs et utilisatrices peuvent rapidement générer des rapports ad hoc pour répondre à des questions spécifiques ou explorer les tendances des données sans avoir recours à un long processus de création de rapports.

- **Tableaux de bord** : les données extraites de CJA peuvent être utilisées pour créer des tableaux de bord et des visualisations Excel pour une vue d’ensemble générale des indicateurs clés de performances (KPI).

- **Partage des informations** : vous pouvez partager des rapports et des informations Excel avec des personnes membres de l’équipe ou des parties prenantes qui ne disposent peut-être pas d’un accès direct à CJA.

## Vidéo de vue d’ensemble

>[!IMPORTANT]
>
>Cette vidéo de présentation présente l’interface utilisateur du Report Builder dans Customer Journey Analytics. Certaines différences d’interface utilisateur et de terminologie existent. Dans le cas contraire, l’expérience utilisateur est identique.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

Vous pouvez télécharger le Report Builder à partir du [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
