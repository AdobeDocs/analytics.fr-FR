---
description: Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.
title: Planification d’une requête de données
topic: Report builder
uuid: f6d8c90f-e185-4d60-8035-f20f74bfcd89
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Planification de classeurs

Vous pouvez planifier des classeurs, définir des options de remise avancées, indiquer des destinataires et afficher l’historique de planification. Les options de remise avancées vous permettent de configurer des classeurs à envoyer à une heure précise ou à des intervalles déterminés. Vous avez également la possibilité d’indiquer le format de fichier pour l’envoi du classeur.

Ainsi, vous pouvez planifier la remise immédiate des classeurs ou leur diffusion selon un schéma récurrent et spécifier le format de fichier dans [!DNL Advanced Delivery Options]. La taille du fichier est limitée à 5 Mo pour l’envoi d’un classeur.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**. (Voir [Planification et distribution de rapports](/help/analyze/reports-analytics/scheduling.md) dans l’aide de Reports &amp; Analytics.)

>[!NOTE] Pour qu’il soit possible de planifier un classeur, Excel 2007 ou le module de compatibilité doit être installé. Le nombre maximal de classeurs planifiés par licence de Report Builder est de 10. Néanmoins, vous pouvez augmenter ce nombre en utilisant des classeurs d’autres licences. Pour ce faire, sélectionnez **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Report Builder Reports]**. Un classeur qui a été planifié (ou transféré dans la bibliothèque de classeurs) mais qui n’a pas été modifié (mis à jour ou remplacé) depuis plus de 28 mois sera supprimé.

>[!NOTE] La valeur « Heure de remise »/« Heure de la journée » entrée par l’utilisateur indique l’heure à laquelle le classeur doit commencer le traitement, et non l’heure à laquelle il sera réellement remis. Le temps réel de remise du classeur dépend principalement du temps nécessaire au traitement (le traitement des classeurs complexes et volumineux prend plus de temps que celui des classeurs plus simples). Si, par exemple, le traitement d’un classeur prend 15 minutes, le temps de remise réel est au moins de 15 minutes après le délai de remise initialement spécifié.
>En outre, un certain nombre d’autres facteurs peuvent allonger le délai de remise du classeur :
>
> * **L’exécution simultanée de plusieurs planifications différentes du même type** peut entraîner une surcharge du système. Le système de planification ne permet l’exécution simultanée que de quelques classeurs (5 à 10) de n’importe quel type. Par conséquent, lorsque plus de 5 à 10 classeurs sont programmés à la fois, certains devront attendre que d’autres classeurs soient terminés avant de pouvoir commencer le traitement. Ce problème peut être réglé en planifiant les classeurs d’une entreprise à des heures décalées tout au long de la journée ou étalés sur une heure, plutôt que de tout lancer en même temps.
> * Outre leur type, les classeurs se mettent également en file d’attente si l’entreprise dispose de **plus de 15 à 20 classeurs planifiés simultanément, quel que soit leur type**. Ceci peut être évité en échelonnant les heures de planification au lieu d’avoir plusieurs lancements en même temps.
> * **Des problèmes sur des services en aval** sur lesquels repose le planificateur peuvent également affecter la livraison des classeurs. Par exemple, si vous utilisez indépendamment les API pour exécuter des classeurs et remplir la file d’attente des demandes d’API, vos classeurs planifiés peuvent être remis lentement car il y a une concurrence pour cette ressource.
> * **Une latence des suites de rapports** (un retard dans la collecte des données) peut également retarder certains classeurs planifiés.


## Planification d’un classeur

1. Générez un classeur et enregistrez-le.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   The [!UICONTROL Scheduled Reports] tab summarizes all the tasks you have created, as well as the number of remaining tasks.
1. Sur l’ **[!UICONTROL Scheduled Reports]** onglet, cliquez sur **[!UICONTROL New]**.
1. L’Assistant de planification - Options de base s’affiche :

   ![](assets/simple-schedule-wizard.png)

1. Dans la [!UICONTROL Basic Scheduling Wizard], configurez les options suivantes :

| Champ | Description |
|--- |--- |
| Sélectionner le rapport | Nom du classeur. Pour les nouveaux rapports planifiés, ce champ est rempli avec le nom du classeur actif. |
| Sélectionner | Affiche la page Sélectionner le rapport. Vous pouvez sélectionner un rapport sur le serveur (où sont stockés tous les classeurs déjà programmés) ou sur votre machine locale. Si vous sélectionnez un classeur sur le disque local au format .xls, le système convertit le fichier au format .xlsx. Dans le cadre de cette conversion, le fichier est ouvert dans Excel et rendu actif. Si le classeur sélectionné pour le rapport planifié porte le même nom de fichier que le classeur actuellement ouvert dans Excel, le système sélectionne le fichier local au lieu du fichier précédemment téléchargé. Si vous sélectionnez un rapport dans le référentiel de planification, une copie du classeur est créée sur le serveur (le chiffre 1 est ajouté à son nom de fichier). Le nouveau rapport planifié utilise le classeur copié. |
| Personnaliser | Permet de personnaliser le format de date. |
| À | Affiche votre carnet d&#39;adresses Outlook, le cas échéant. |
| Envoyer à : Courriel | Adresse électronique du destinataire du classeur. |
| Envoyer à :  de publication | Affiche un  de de distribution disponible  pour ce. |
| Power BI | Voir [Publier le classeur sur Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) pour plus d’informations. |
| Sujet | Description définie par l’utilisateur. |
| Planification | Vous permet d’indiquer le moment où le classeur doit être envoyé (Immédiatement, Horaire, Quotidiennement, Hebdomadairement, Mensuellement et Annuellement). |

## Options de remise avancées

1. Cliquez sur **[!UICONTROL Advanced Delivery Options]** pour configurer les options de fichier et de publication :

| Champ | Description |
|--- |--- |
| Onglet **Planification** |  |
| Heure de remise | Cette option permet d’envoyer immédiatement le classeur ou de planifier une remise différée. L’heure dépend du fuseau horaire défini sur votre ordinateur. |
| Modèle de répétition | Le classeur est envoyé sur la base des options sélectionnées. |
| Plage de répétition | Vous permet d’indiquer les heures de début et de fin de réception du classeur.   Remarque : si vous planifiez un classeur le premier jour d’une période en cours (semaine, mois, trimestre ou année), le système renverra uniquement les données relatives à ce jour. |
| Onglet **Options de fichier** |  |
| Format du fichier | Permet de sélectionner le format de remise : Excel 2007 (.xlsx) ou 2003 (.xls), .pdf, .csv, .mht, .txt et .xml. |
| Destination du fichier | Indique Courriel ou FTP. Les options de la page changent en fonction de votre sélection. Pour FTP, vous devez vous assurer que l’hôte est disponible en externe. |
| Liste de publication | Si vous envoyez le classeur planifié à plusieurs listes de publication, il s’exécute une fois pour chaque liste. Les suites de rapports variables sont remplacées par celle qui est affectée à la liste de publication. |
| Langue du contenu du fichier | Indique la langue que vous souhaitez utiliser pour la lettre d’envoi. Vous pouvez sélectionner chinois (simplifié ou traditionnel), allemand, français, japonais, coréen, portugais brésilien ou espagnol. |
| Onglet **Options de publication** |  |
| Publication sur Power BI | <ul><li>Publier le classeur sur Power BI</li><li>Publier toutes les requêtes du Report Builder sous forme de jeux de données Power BI</li><li>Publier tous les tableaux formatés sous forme de jeux de données Power BI</li></ul> |
| Nommer ce rapport Power BI comme | Détails de l’étiquette |

1. Cliquez sur **[!UICONTROL OK]**, puis sur **[!UICONTROL Exit]**.

   Le Report Builder affiche le classeur planifié dans le [Gestionnaire de tâches planifiées](/help/analyze/report-builder/r-arb-scheduled-reports.md).

