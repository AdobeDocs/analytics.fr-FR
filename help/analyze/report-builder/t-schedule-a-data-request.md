---
description: Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.
seo-description: Vous pouvez planifier l’envoi des rapports en fonction de l’heure et du format de fichier définis.
seo-title: Planification d'une requête de données
solution: Analytics
title: Planification d'une requête de données
topic: Créateur de rapports
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: ed8cfa41a2495c884f1096ea54624820bf3a9e07

---


# Planification des classeurs

Vous pouvez planifier des classeurs, définir des options de remise avancées, définir des destinataires et afficher l'historique de planification. Les options de remise avancées vous permettent de configurer des classeurs à envoyer à un moment ou à des intervalles spécifiques. Vous pouvez également spécifier le format de fichier dans lequel envoyer le classeur.

For example, you can schedule workbooks to be delivered immediately or on a recurring schedule, and specify the file format in [!DNL Advanced Delivery Options]. La taille du fichier est limitée à 5 Mo pour le chargement d'un classeur.

Additionally, after you create a workbook schedule in Report Builder, you can view and edit the schedule in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]**. (Voir [Planification et distribution de rapports](/help/analyze/reports-analytics/scheduling.md) dans l’aide de Rapports et analyses.)

>[!NOTE]
>
>Pour pouvoir planifier un classeur, Excel 2007 ou le pack de compatibilité doit être installé. La licence du créateur de rapports peut contenir au maximum 10 classeurs planifiés. Néanmoins, vous pouvez augmenter ce nombre en utilisant des classeurs d’autres licences. To do so, go to **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Report Builder Reports]**. Un classeur planifié (ou téléchargé dans la Bibliothèque des classeurs) et qui n'a pas été modifié (mis à jour, remplacé) depuis plus de 28 mois sera supprimé.

>[!NOTE]
>
>Le « Délai de remise »/« Heure de la journée » saisi par l'utilisateur indique l'heure à laquelle le classeur doit commencer, et non le temps qu'il doit effectivement être diffusé. Le temps réel de diffusion du classeur dépend principalement du temps nécessaire au traitement (les classeurs complexes et volumineux prennent plus de temps à traiter que les classeurs plus simples). Par exemple, si le traitement d'un classeur prend 15 minutes, l'heure de remise réelle est d'au moins 15 minutes au-delà de l'heure de remise spécifiée/Heure.
>En outre, un certain nombre d'autres facteurs peuvent encore accroître le délai avant que le classeur soit réellement diffusé :
>
> * **L'exécution simultanée de plusieurs planifications du même type** peut surcharger le système. Le système de planification autorise uniquement certains (5-10) classeurs d'un type à exécuter simultanément. De ce fait, lorsque plus de 5-10 sont tous planifiés simultanément, certains doivent attendre la fin de leur traitement pour que d'autres classeurs puissent commencer le traitement. Ce problème peut être atténué en planifiant les classeurs d'une entreprise à des moments échelonnés tout au long de la journée ou de l'heure, plutôt que simultanément.
> * Outre le type de classeur spécifique, les classeurs attendent également en ligne si l'entreprise compte **plus de 15-20 parmi tous les types de classeurs planifiés à la fois (pour tous les différents types de classeurs)**. Cela peut être atténué en utilisant des heures de planification stupéfiantes plutôt que d'avoir beaucoup d'exécutions au même moment.
> * **Les problèmes des services** en aval auxquels le planificateur fait appel peuvent également affecter la remise des classeurs. Par exemple, si vous utilisez indépendamment les API pour exécuter des classeurs et remplissez la file d'attente des demandes d'API, les classeurs planifiés peuvent être lents pendant que vous faites concurrence pour cette ressource.
> * **La latence des suites de rapports** (un délai dans la collecte de données) peut également retarder certains classeurs planifiés.


## Planification d’un classeur

1. Générez et enregistrez un classeur.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   L’onglet [!UICONTROL Rapports programmés] affiche un récapitulatif de toutes les tâches que vous avez créées, ainsi que le nombre de tâches restantes.
1. Sur l’onglet **Rapports programmés**, cliquez sur **[!UICONTROL Nouveau]**.
1. L’Assistant de planification - Options de base s’affiche :

   ![](assets/simple-schedule-wizard.png)

1. Dans [!UICONTROL l’Assistant de planification - Options de base], configurez les options suivantes :

| Champ | Description |
|--- |--- |
| Sélectionner le rapport | Nom du classeur. Dans le cas des nouveaux rapports programmés, ce champ contient le nom du classeur actif. |
| Sélectionner | Affiche la page Sélectionner le rapport. Vous pouvez sélectionner un rapport sur le serveur (où sont stockés tous les classeurs déjà programmés) ou sur votre machine locale. Si vous sélectionnez un classeur sur le disque local au format .xls, le système convertit le fichier au format .xlsx. Dans le cadre de cette conversion, le fichier est ouvert dans Excel et rendu actif. Si le classeur sélectionné pour le rapport planifié porte le même nom de fichier que celui ouvert actuellement dans Excel, le système sélectionne le fichier local au lieu de celui transféré précédemment. Si vous sélectionnez un rapport dans le référentiel de planification, une copie du classeur est créée sur le serveur, avec le nom de fichier mis à jour avec 1. Le rapport planifié nouvellement créé utilise le classeur copié. |
| Personnaliser | Vous permet de personnaliser le format de date. |
| A | Affiche le Carnet d’adresses Outlook, le cas échéant. |
| Envoyer à : Courriel | Destinataire électronique du classeur. |
| Envoyer à : Liste de publication | Répertorie les listes de distribution disponibles pour cette société. |
| Power BI | Voir [Publier le classeur sur Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/integration-power-bi.md) pour en savoir plus. |
| Objet | Description définie par l’utilisateur. |
| Planification | Vous permet de spécifier le moment auquel envoyer le classeur. (Immédiatement, Horaire, Quotidiennement, Hebdomadairement, Mensuellement et Annuellement). |

## Options de remise avancées

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

| Champ | Description |
|--- |--- |
| Onglet **Planification** |  |
| Heure de remise | Vous permet de planifier le classeur immédiatement ou pour une date ultérieure. L’heure indiquée est fonction du fuseau horaire défini sur votre ordinateur. |
| Modèle de répétition | Envoie le classeur en fonction de vos sélections. |
| Plage de répétition | Vous permet de spécifier le moment de début et d'arrêt de la réception du classeur. Remarque : La planification d'un classeur le premier jour d'une période en cours (semaine, mois, trimestre ou année) renvoie uniquement les données du premier jour. |
| Onglet **Options de fichier** |  |
| Format du fichier | Permet de sélectionner le format de remise : Excel 2007 (.xlsx) ou 2003 (.xls), .pdf, .csv, .mht, .txt et .xml. |
| Description du fichier | Précise E-mail ou FTP. Les options disponibles sur cette page varient en fonction de la sélection. Dans le cas de FTP, vous devez vous assurer que l’hôte est disponible en externe. |
| Liste de publication | Si vous envoyez le classeur planifié à plusieurs listes de publication, le classeur s'exécute une fois pour chaque liste. Les suites de rapports variables sont remplacées par celle qui est affectée à la liste de publication. |
| Langue du contenu du fichier | Indique la langue que vous souhaitez utiliser pour la lettre d’envoi. Vous avez le choix entre l’allemand, le portugais (du Brésil), le chinois (simplifié ou traditionnel), le coréen, l’espagnol, le français ou le japonais. |
| Onglet **Options de publication** |  |
| Publication sur Power Bi | <ul><li>Publier le classeur sur Power BI</li><li>Publier toutes les requêtes du Créateur de rapports sous forme de jeux de données Power BI</li><li>Publier tous les tableaux formatés sous forme de jeux de données Power BI</li></ul> |
| Intituler ce rapport Power BI par | Informations d’intitulé |

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   Report Builder displays the scheduled workbook in the [Scheduled Task Manager](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).

