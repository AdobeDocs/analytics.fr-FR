---
title: Vue d’ensemble de Report Builder
description: Décrit la fonctionnalité de Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---

# Vue d’ensemble de Report Builder

Le nouveau complément Report Builder JavaScript, initialement disponible uniquement dans Customer Journey Analytics, est désormais également présent dans Adobe Analytics. Cette nouvelle version présente plusieurs avantages :

- Trouvez des informations dans Excel plus rapidement et plus facilement grâce à des workflows améliorés pour la création et la gestion des blocs de données, avec une plus grande flexibilité des blocs de données.
- Sur plusieurs plateformes : vous n’avez plus besoin de vous connecter à votre machine virtuelle pour utiliser Report Builder, car nous prenons désormais en charge PC, Mac et Excel Online.
- Moins de temps à attendre le retour des blocs de données, grâce à la mise à niveau de l’API 2.0
- Amélioration de la vitesse.

Les utilisateurs et utilisatrices de l’outil Report Builder hérité peuvent [convertir des classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) pour le nouveau Report Builder.

Report Builder vous permet de créer, de modifier et d’actualiser facilement des rapports personnalisés à l’aide des données Adobe Analytics. Grâce à lʼinterface d’utilisation simple et flexible de Report Builder, qui permet de faire glisser et déposer des éléments, vous pouvez créer des requêtes de données complexes et des rapports personnalisés à partir de données Adobe Analytics, sans quitter Excel.

Avec Report Builder, vous pouvez réaliser les actions suivantes :

- Référencement des cellules de feuille de calcul existantes pour obtenir lʼordre de lignes, la période ou le filtre parfait
- Création de dates personnalisées à lʼaide du calendrier, des références de cellules ou des mathématiques de date
- Conception de vos tableaux et visualisations avec des outils familiers de formatage Excel

## Utilisation côte à côte de la version héritée de Report Builder et de la nouvelle version de Report Builder

Vous pouvez toujours utiliser les deux versions de Report Builder, en tenant compte des avertissements suivants :

- N’utilisez pas les deux versions de Report Builder sur le même fichier en même temps. Elles s’excluent mutuellement.
- Vous pouvez toujours utiliser la version héritée de Report Builder sur les classeurs hérités et la nouvelle version de Report Builder sur les nouveaux classeurs.
- En outre, vous pouvez automatiquement [convertir les classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) au nouveau format Report Builder. Avant cela, dupliquez et renommez le fichier.

## Fonctionnalités héritées de Report Builder non prises en charge dans la nouvelle version de Report Builder

Lorsque vous comparez la fonctionnalité de la version héritée de Report Builder au nouveau complément Report Builder, certaines fonctionnalités héritées ne sont plus disponibles :

- Requêtes en temps réel

- Rapports Chemin/Abandon

- Option FTP pour les rapports planifiés

- Mesures Visiteurs et visiteuses. Les mesures suivantes seront toutes converties en « visiteurs et visiteuses uniques », même si le résultat du compte rendu des performances peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cela s’applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.

## Cas d’utilisation courants

- **Extraction des données** : Adobe Report Builder vous permet d’extraire des données depuis Adobe Analytics vers Excel. Vous pouvez créer des rapports et des requêtes personnalisés pour récupérer des points de données spécifiques pertinents pour votre analyse.

- **Rapports personnalisés** : vous pouvez concevoir et formater des rapports personnalisés dans Excel en fonction de vos besoins spécifiques en matière de rapports. Cela s’avère particulièrement utile pour adapter les rapports aux différentes parties prenantes.

- **Analyse ad hoc** : les utilisateurs et utilisatrices peuvent rapidement générer des rapports ad hoc pour répondre à des questions spécifiques ou explorer les tendances des données sans avoir recours à un long processus de création de rapports.

- **Tableaux de bord** : les données extraites de CJA peuvent être utilisées pour créer des tableaux de bord et des visualisations Excel pour une vue d’ensemble générale des indicateurs clés de performances (KPI).

- **Partage des informations** : vous pouvez partager des rapports et des informations Excel avec des personnes membres de l’équipe ou des parties prenantes qui ne disposent peut-être pas d’un accès direct à CJA.

## Vidéo de vue d’ensemble

>[!IMPORTANT]
>
>Cette vidéo de vue d’ensemble présente l’interface d’utilisation de Report Builder dans Customer Journey Analytics. Certaines différences d’interface d’utilisation et de terminologie existent. Pour le reste, l’expérience d’utilisation est identique.


>[!BEGINSHADEBOX]

Consultez ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Vue d’ensemble de Report Builder](https://video.tv.adobe.com/v/337569?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]

Vous pouvez télécharger Report Builder à partir du [Microsoft Store](https://appsource.microsoft.com/fr-fr/product/office/WA200003101?tab=Overview).
