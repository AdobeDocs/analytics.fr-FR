---
title: Comment convertir vos classeurs de Report Builder hérités en bases de données
description: Décrit comment convertir vos requêtes héritées en bases de données.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: eedabc6295f9b918e1e00b93993680e676c216c3
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Conversion de classeurs de Report Builder hérités en blocs de données

Dans le cadre de la transition vers une nouvelle technologie de Report Builder, vous pouvez rapidement convertir vos classeurs hérités actuels en classeurs basés sur JavaScript.

>[!IMPORTANT]
>
>Dupliquez chaque classeur et renommez une version avant de le convertir. Ainsi, vous disposez toujours d’une copie du classeur d’origine si vous en avez besoin.

>[!VIDEO](https://video.tv.adobe.com/v/3434957/?quality=12&learn=on)

1. Configurez le nouveau Report Builder en [suivant ces instructions](/help/analyze/report-builder/report-builder-setup.md).

1. Ouvrez Excel et cliquez sur l’icône Adobe Report Builder en haut à droite.

1. Cliquez sur **[!UICONTROL Login]** et connectez-vous au Report Builder.

1. Le module complémentaire Report Builder détecte si ce classeur contient des requêtes [Report Builder hérité](/help/analyze/legacy-report-builder/home.md).

   ![invite de mise à niveau du classeur](assets/upgrade_workbook.png)

1. Si une ou plusieurs requêtes héritées sont trouvées, cliquez sur **[!UICONTROL Mettre à niveau]** pour mettre à niveau un classeur.

   >[!NOTE]
   >
   >Vous devez mettre à niveau chaque requête individuellement. La mise à niveau en bloc n’est pas prise en charge.


1. Si vous effectuez une mise à niveau, un avertissement s’affiche pour vous avertir des modifications apportées au classeur. Il vous invite également à créer une sauvegarde de votre classeur hérité avant de poursuivre.

   ![avertissement de mise à niveau](assets/upgrade_warning.png)

1. Cliquez sur **[!UICONTROL Continuer]** pour poursuivre la mise à niveau.

   Si la mise à niveau est réussie, le message d’achèvement suivant s’affiche :

   ![mise à niveau terminée](assets/upgrade_complete.png)

1. (Facultatif) Cliquez sur **[!UICONTROL Télécharger le rapport de mise à niveau]**. Ce rapport contient l&#39;état de chaque bloc de données mis à niveau.

Vous pouvez désormais [gérer le bloc de données](/help/analyze/report-builder/manage-reportbuilder.md).


## Fonctionnalités de Report Builder héritées non prises en charge dans le nouveau Report Builder

Lors de la comparaison des fonctionnalités du Report Builder hérité au nouveau module complémentaire de Report Builder, certaines fonctionnalités héritées ne sont plus disponibles :

- Requêtes en temps réel

- Rapports Chemin/Abandon

- Option FTP pour les rapports planifiés

- Mesures des visiteurs. Les mesures suivantes seront toutes converties en &quot;visiteurs uniques&quot;, même si le résultat du rapport peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cela s&#39;applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.
