---
title: Comment convertir vos classeurs Report Builder hérités en blocs de données
description: Décrit comment convertir vos requêtes héritées en blocs de données
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 22%

---

# Conversion des classeurs Report Builder hérités en blocs de données

Dans le cadre de la transition vers une nouvelle technologie Report Builder, vous pouvez rapidement convertir vos classeurs hérités actuels en classeurs basés sur JavaScript.

>[!IMPORTANT]
>
>Dupliquez chaque classeur et renommez une version avant de la convertir. De cette façon, vous disposez toujours d’une copie du classeur d’origine, si vous en avez besoin.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://video.tv.adobe.com/v/3434957?quality=12&learn=on){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]



1. Configurez le nouveau Report Builder en [suivant ces instructions](/help/analyze/report-builder/report-builder-setup.md).

1. Ouvrez Excel et cliquez sur l’icône Adobe Report Builder en haut à droite.

1. Cliquez sur **[!UICONTROL Connexion]** et connectez-vous à Report Builder.

1. Le complément Report Builder détecte si ce classeur contient des requêtes [Report Builder héritées](/help/analyze/legacy-report-builder/home.md).

   ![invite de mise à niveau du classeur](assets/upgrade_workbook.png)

1. Si une ou plusieurs requêtes héritées sont trouvées, cliquez sur **[!UICONTROL Mettre à niveau]** pour mettre à niveau un classeur.

   >[!NOTE]
   >
   >Vous devez mettre à niveau chaque demande individuellement. La mise à niveau en bloc n’est pas prise en charge.


1. Un avertissement s’affiche pour vous avertir des modifications apportées au classeur en cas de mise à niveau. Il vous invite également à créer une sauvegarde de votre classeur hérité avant de continuer.

   ![ avertissement de mise à niveau ](assets/upgrade_warning.png)

1. Cliquez sur **[!UICONTROL Continuer]** pour poursuivre la mise à niveau.

   Si la mise à niveau est réussie, l’avis d’achèvement suivant s’affiche :

   ![mise à niveau terminée](assets/upgrade_complete.png)

1. (Facultatif) Cliquez sur **[!UICONTROL Télécharger le rapport de mise à niveau]**. Ce rapport contient le statut de chaque bloc de données mis à niveau.

Vous pouvez désormais [gérer le bloc de données](/help/analyze/report-builder/manage-reportbuilder.md).


## Fonctionnalités héritées de Report Builder non prises en charge dans la nouvelle version de Report Builder {#unsupported}

Lorsque vous comparez la fonctionnalité de la version héritée de Report Builder au nouveau complément Report Builder, certaines fonctionnalités héritées ne sont plus disponibles :

- Requêtes en temps réel

- Rapports Chemin/Abandon

- Option FTP pour les rapports planifiés

- Mesures Visiteurs et visiteuses. Les mesures suivantes seront toutes converties en « visiteurs et visiteuses uniques », même si le résultat du compte rendu des performances peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cela s’applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.

## Planifier un classeur converti {#schedule}

Voir [Planification d’un classeur converti](/help/analyze/report-builder/schedule-reportbuilder.md) dans l’article de planification.