---
title: Qu’est-ce que le nouveau Adobe Report Builder ?
description: Décrit la nouvelle fonctionnalité de Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 7e8a25381f2eadafc5dc22a0991060ea475b5d43
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 27%

---

# À propos du nouveau Adobe Report Builder

Le nouveau module complémentaire de Report Builder JavaScript, initialement disponible uniquement en Customer Journey Analytics, est désormais également introduit dans Adobe Analytics. Cette nouvelle version présente plusieurs avantages :

- Obtenez plus rapidement et plus facilement des informations dans Excel grâce à des workflows améliorés pour la création et la gestion des blocs de données, notamment une plus grande flexibilité des blocs de données.
- Plateforme : plus de connexion à votre machine virtuelle pour utiliser le Report Builder, car nous prenons désormais en charge PC, Mac et Excel Online.
- Moins de temps d’attente pour le retour des blocs de données, grâce à la mise à niveau de l’API 2.0
- Amélioration de la vitesse.

>[!NOTE]
>
>La planification des classeurs pour cette version de Report Builder sur Adobe Analytics n’a pas encore été publiée, mais sera disponible début 2025. Vous pouvez commencer maintenant à utiliser des classeurs qui ne nécessitent pas de planification.

Les utilisateurs de l’outil de Report Builder hérité peuvent [ convertir des classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) en nouveau Report Builder.

Report Builder vous permet de créer, modifier et actualiser facilement des rapports personnalisés à l’aide de données Adobe Analytics. Grâce à l’interface utilisateur par glisser-déposer simple et flexible de Report Builder, vous pouvez créer des requêtes de données complexes et des rapports personnalisés à partir de données Adobe Analytics, le tout dans Excel.

Avec Report Builder, vous pouvez :

- Référencement des cellules de feuille de calcul existantes pour obtenir lʼordre de lignes, la période ou le filtre parfait
- Création de dates personnalisées à lʼaide du calendrier, des références de cellules ou des mathématiques de date
- Conception de vos tableaux et visualisations avec des outils familiers de formatage Excel

## Utilisation côte à côte du Report Builder hérité et du nouveau Report Builder

Vous pouvez toujours utiliser les deux versions de Report Builder, avec les avertissements suivants :

- N’utilisez pas les deux versions de Report Builder sur le même fichier en même temps. Elles s&#39;excluent mutuellement.
- Vous pouvez toujours utiliser le Report Builder hérité sur les classeurs hérités et le nouveau Report Builder sur les nouveaux classeurs.
- De plus, vous pouvez automatiquement [ convertir les classeurs hérités](/help/analyze/report-builder/convert-workbooks.md) au nouveau format de Report Builder. Avant cela, dupliquez et renommez le fichier.

## Fonctionnalités de Report Builder héritées non prises en charge dans le nouveau Report Builder

Lors de la comparaison des fonctionnalités du Report Builder hérité au nouveau module complémentaire de Report Builder, certaines fonctionnalités héritées ne sont plus disponibles :

- Requêtes en temps réel

- Rapports Chemin/Abandon

- Option FTP pour les rapports planifiés

- Mesures des visiteurs. Les mesures suivantes seront toutes converties en &quot;visiteurs uniques&quot;, même si le résultat du rapport peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cela s&#39;applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.

## Cas d’utilisation courants

- **Extraction de données** : Adobe Report Builder vous permet d’extraire des données d’Adobe Analytics dans Excel. Vous pouvez créer des rapports et des requêtes personnalisés pour récupérer des points de données spécifiques pertinents pour votre analyse.

- **Rapports personnalisés** : vous pouvez concevoir et formater des rapports personnalisés dans Excel en fonction de vos besoins spécifiques en matière de rapports. Cela s’avère particulièrement utile pour adapter les rapports aux différentes parties prenantes.

- **Analyse ad hoc** : les utilisateurs et utilisatrices peuvent rapidement générer des rapports ad hoc pour répondre à des questions spécifiques ou explorer les tendances des données sans avoir recours à un long processus de création de rapports.

- **Tableaux de bord** : les données extraites de CJA peuvent être utilisées pour créer des tableaux de bord et des visualisations Excel pour une vue d’ensemble générale des indicateurs clés de performances (KPI).

- **Partage des informations** : vous pouvez partager des rapports et des informations Excel avec des personnes membres de l’équipe ou des parties prenantes qui ne disposent peut-être pas d’un accès direct à CJA.

## Vidéo de vue d’ensemble

>[!IMPORTANT]
>
>Cette vidéo de présentation présente l’interface utilisateur du Report Builder en Customer Journey Analytics. La terminologie et l’interface utilisateur diffèrent. Sinon, l’expérience utilisateur est identique.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

Vous pouvez télécharger le Report Builder à partir du [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
