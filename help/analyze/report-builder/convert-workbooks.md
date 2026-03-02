---
title: Convertir les classeurs Report Builder hérités
description: Découvrez comment migrer et convertir les classeurs Report Builder hérités en nouveau Report Builder. Suivez les instructions détaillées de ce guide de migration pour convertir en toute transparence vos classeurs Adobe Analytics.
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: ff9011b2-fc18-456f-81dc-151b9e4fccd2
source-git-commit: 9743d7ac2a6c7e63d7a6701e60d05683c5680d36
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# Conversion des classeurs Report Builder hérités

L’ancien Report Builder arrive en fin de vie en juin 2026. Vous devez migrer vos classeurs de l’ancien Report Builder vers le nouveau Report Builder. Le nouveau Report Builder offre un moyen pratique de migrer rapidement les classeurs créés avec l’ancien Report Builder.

>[!IMPORTANT]
>
>Dupliquez chaque classeur et renommez une version avant de convertir l’ancien classeur. Vous disposez ainsi toujours d’une copie du classeur hérité d’origine, si vous en avez besoin.


>[!BEGINSHADEBOX]

Voir ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Convert workbooks](https://experienceleague.adobe.com/fr/docs/analytics-learn/tutorials/exporting/report-builder/upgrade-and-reschedule-workbooks){target="_blank"} pour une vidéo de démonstration.

>[!ENDSHADEBOX]


>[!NOTE]
>
>Pour convertir des classeurs hérités, vous devez d’abord [configurer le nouveau Report Builder](/help/analyze/report-builder/report-builder-setup.md).


## Ouvrir un classeur hérité

Pour ouvrir un classeur hérité, vous pouvez :

* Ouvrez un classeur hérité planifié dans l’onglet **[!UICONTROL Planifier]** du hub [Report Builder](report-builder-hub.md). Il s’agit de la méthode recommandée pour les classeurs hérités planifiés. Vous avez la possibilité d’utiliser la planification associée au classeur hérité dès que vous [planifiez le classeur hérité converti](#schedule-a-converted-legacy-workbook).

   1. Ouvrez [!DNL Excel] et sélectionnez ![AdobeLogoRedonWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dans la barre de ruban [!DNL Excel].

   1. Sélectionnez **[!UICONTROL Connexion]** et connectez-vous à Report Builder.

   1. Sélectionnez **[!UICONTROL Planifier]** dans le hub [Report Builder](report-builder-hub.md).
   1. Sélectionnez l’onglet **[!UICONTROL Hérité]**. Cet onglet répertorie les classeurs planifiés Report Builder hérités que vous avez créés.

      ![Classeurs hérités](assets/upgrade-legacy-schedule.png)

   1. Sélectionnez ![SelectBox](/help/assets/icons/SelectBox.svg) le classeur planifié à convertir dans la liste, puis sélectionnez ![Télécharger](/help/assets/icons/Download.svg). Le classeur est téléchargé et s’ouvre dans une nouvelle fenêtre dans [!DNL Excel]. Vous pouvez désormais [convertir l’ancien classeur Report Builder](#convert-a--workbook).


* Ouvrez un classeur hérité directement depuis votre ordinateur ou réseau local. Lorsque vous utilisez cette méthode, il ne vous est pas proposé d’utiliser la planification qui peut être associée au classeur hérité. <br/>Lorsque le classeur hérité est ouvert dans [!DNL Excel] :

   1. Sélectionnez ![AdobeLogoRedOnWhite](/help/assets/icons/AdobeLogoRedOnWhite.svg) **[!UICONTROL Report Builder]** dans la barre de ruban [!DNL Excel].
   1. Sélectionnez **[!UICONTROL Connexion]** et connectez-vous à Report Builder.
   1. Convertissez ensuite [ classeur hérité](#convert-a-workbook).


## Convertir un classeur hérité

Pour convertir votre classeur hérité :

1. Une fois que vous avez ouvert un classeur hérité, le nouveau Report Builder détecte si ce classeur contient des requêtes [Report Builder héritées](/help/analyze/legacy-report-builder/home.md).

   ![Capture d’écran du rapport de mise à niveau [!DNL Excel] Report Builder présentant la mise à niveau de la migration](assets/upgrade-workbook.png){zoomable="yes"}

1. Si une ou plusieurs requêtes héritées sont trouvées, cliquez sur **[!UICONTROL Mettre à niveau]** dans la boîte de dialogue **[!UICONTROL Mettre à niveau le classeur]** pour mettre à niveau le classeur.

   >[!NOTE]
   >
   >Vous devez mettre à niveau chaque demande individuellement. La mise à niveau en bloc n’est pas prise en charge.


1. Une boîte de dialogue **[!UICONTROL Avertissement]** s’affiche pour vous avertir des modifications apportées au classeur en cas de mise à niveau. Il vous invite également à créer une sauvegarde de votre classeur hérité avant de continuer.

   ![Capture d’écran du rapport de mise à niveau de [!DNL Excel] Report Builder affichant l’avertissement de migration](assets/upgrade-warning.png){zoomable="yes"}

1. Cliquez sur **[!UICONTROL Continuer]** pour poursuivre la mise à niveau.

   Si la mise à niveau est réussie, une notification **[!UICONTROL La mise à niveau du classeur est maintenant terminée]** s’affiche.

   ![Copie d’écran du rapport de mise à niveau de [!DNL Excel] Report Builder montrant la migration terminée](assets/upgrade-complete.png)

   * Sélectionnez **[!UICONTROL Fermer]** pour fermer la notification et continuer à travailler dans le classeur avec les demandes mises à jour pour le nouveau Report Builder.

   * Sélectionnez **[!UICONTROL Télécharger le rapport de mise à niveau]** pour télécharger et ouvrir un nouveau classeur [!DNL Excel] qui affiche le résultat de la mise à niveau. Pour obtenir un exemple, reportez-vous à la section ci-dessous.

     ![Capture d’écran du rapport de mise à niveau de [!DNL Excel] Report Builder affichant le rapport de migration](assets/upgrade-report.png)

Vous pouvez désormais [gérer les blocs de données](/help/analyze/report-builder/manage-reportbuilder.md) dans le classeur. Ces blocs de données sont le résultat de la mise à niveau et remplacent vos requêtes Report Builder héritées.


## Planifier un classeur hérité converti

Vous avez la possibilité d’utiliser les détails de la planification du classeur hérité que vous avez téléchargé et ouvert à partir de l’onglet **[!UICONTROL Planification]** dans le hub Report Builder. Cette option n’est pas disponible pour les classeurs hérités avec les détails de planification que vous ouvrez depuis votre ordinateur ou réseau local.

1. Pour planifier un classeur hérité converti avec une planification héritée :

   * Sélectionnez **[!UICONTROL Envoyer le classeur]** dans le hub Report Builder, ou
   * Sélectionnez **[!UICONTROL Planifier le classeur]** dans l’onglet **[!UICONTROL Classeurs]** disponible dans l’onglet **[!UICONTROL Planifications]** de Report Builder.

1. Vous pouvez utiliser les détails de planification du classeur hérité comme paramètres de planification par défaut.

   ![Capture d’écran des options des paramètres de planning hérités de [!DNL Excel] Report Builder](assets/upgrade-legacy-schedule-convert.png)

   * Sélectionnez **[!UICONTROL Utiliser]** pour utiliser les détails du planning hérité. Les détails du planning sont préremplis dans l’interface [ Envoyer le classeur ](schedule-reportbuilder.md#schedule-a-workbook).
   * Sélectionnez **[!UICONTROL Ne pas utiliser]** pour ne pas utiliser les détails du planning hérité.
   * Sélectionnez **[!UICONTROL Annuler]** pour annuler.

   Sélectionnez **[!UICONTROL Supprimer les métadonnées héritées d’une utilisation ultérieure]** pour ne plus utiliser les détails de la planification héritée de ce classeur à l’avenir.


## Migration à partir du Report Builder hérité

Certaines fonctionnalités de l’ancien Report Builder ne sont pas prises en charge, partiellement prises en charge ou implémentées différemment dans Report Builder :

* **Requêtes en temps réel**. Les requêtes en temps réel ne sont pas prises en charge et sont supprimées du classeur hérité converti.

* **Rapports Chemin/Abandon**. Les demandes d’abandon ne sont pas prises en charge et sont supprimées du classeur hérité converti.

* **[!DNL FTP]option pour les rapports planifiés**. L’option permettant de planifier l’envoi des rapports vers un emplacement [!DNL FTP] n’est plus disponible.

* **Option Publier le classeur dans [!DNL Power BI] rapports planifiés**. L’option de planification des rapports à [!DNL Power BI] n’est plus disponible.

* **Mesures Visiteurs**. Les mesures suivantes sont converties en *visiteurs uniques* dans le classeur hérité converti, même si le résultat de la création de rapports peut ne pas correspondre exactement : `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` et `visitorsyearly`. Cette conversion s’applique également à `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` et `mobilevisitorsyearly`.

* **Réauthentification automatique**. Lorsque vous ouvrez un nouveau fichier [!DNL Excel], vous devez vous authentifier à nouveau explicitement. Cette réauthentification est une fonctionnalité de sécurité de la fonctionnalité [!DNL Office Add-ins].

* **Copiez une feuille de calcul avec un groupe de blocs de données**. Pour prendre en charge la copie d’une feuille de calcul contenant plusieurs blocs de données :

   1. Sélectionnez l’onglet de feuille de calcul dans le classeur [!DNL Excel] que vous souhaitez copier.
   1. Dans le menu contextuel de l’onglet, sélectionnez **[!UICONTROL Déplacer ou Copier...]**
   1. Dans la boîte de dialogue **[!UICONTROL Déplacer ou copier]** :
      1. Sélectionnez l&#39;emplacement où vous souhaitez copier la feuille de calcul copiée.
      1. Veillez à activer **[!UICONTROL Créer une copie]**.
      1. Sélectionnez **[!UICONTROL OK]**.
   1. Dans la feuille de calcul source :
      1. Sélectionnez la plage de cellules qui englobe tous les blocs de données.
      1. Sélectionnez ![Copier](/help/assets/icons/Copy.svg) **[!UICONTROL Copier le bloc de données]** dans le hub [Report Builder](/help/analyze/report-builder/report-builder-hub.md).
   1. Dans la feuille de calcul de destination :
      1. Sélectionnez la cellule dans laquelle vous souhaitez coller la plage de cellules copiée.
      1. Sélectionnez ![Coller](/help/assets/icons/Paste.svg) **[!UICONTROL Coller le bloc de données]** dans le hub [Report Builder](/help/analyze/report-builder/report-builder-hub.md).

* **Période**. Report Builder ne migre pas les options de formatage des périodes **[!UICONTROL Afficher la période de début et de fin comme]** appliquées à un libellé de ligne pour une période dans l’ancien Report Builder.

* **Moyenne**. Report Builder ne migre pas l’option de formatage sélectionnée **[!UICONTROL Options moyennes]** (**[!UICONTROL Moyenne quotidienne]** jusqu’à **[!UICONTROL Moyenne annuelle]**) appliquée à une mesure dans l’ancien Report Builder. Utilisez une mesure calculée pour remplacer l’option sélectionnée.

* **Ajouter/ajouter du texte**. Report Builder ne migre pas le **[!UICONTROL Ajouter/ajouter du texte]** appliqué à une mesure dans l’ancien Report Builder.

* **Sous-totaux**. Report Builder ne migre pas l’option de formatage **[!UICONTROL Sous-total(cette demande)]** appliquée à une mesure dans l’ancien Report Builder. Lorsque vous avez utilisé **[!UICONTROL SubTotal(cette requête)]** dans une requête de classeur héritée, la fonctionnalité est convertie en **[!UICONTROL Total]**. Par exemple : dans un bloc de données hérité avec les 5 premiers noms de page, où vous avez utilisé **[!UICONTROL SubTotal(Pages vues)]** pour renvoyer la somme des pages vues pour les 5 premiers noms de page. Après la migration, le même bloc de données avec les 5 premiers noms de page renvoie la somme des pages vues pour *tous* noms de page. Utilisez la fonctionnalité de mesures calculées pour remplacer la fonctionnalité **[!UICONTROL Sous-total]** héritée.
