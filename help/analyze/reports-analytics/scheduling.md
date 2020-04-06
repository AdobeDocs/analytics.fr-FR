---
description: Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.
subtopic: Schedule
title: Planification et distribution des rapports
topic: Reports and analytics
uuid: 1230b0f3-e026-4b83-b231-14d6f75a3836
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Planification et distribution des rapports

Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.

Lorsque vous planifiez un rapport pour les  d’une application Adobe Analytics, vous pouvez utiliser les outils Planification et Distribution pour  les fichiers qui ont été envoyés automatiquement et modifier ou mettre fin à l’.

En raison des différences entre les mécanismes de traitement et les plateformes, les différents types de rapports planifiés et téléchargeables disponibles dans Adobe Analytics présentent différentes limites quant au nombre maximal de lignes qu’ils peuvent traiter dans une seule requête. Voici les limites de chacun :

* Word, CSV, Excel, HTML et PDF : Même nombre de lignes visibles dans le rapport. Par défaut, cette limite est de 50 lignes, mais elle peut atteindre 200. Les rapports de ventilation sont limités à 50 lignes.
* Extraction de données : 50 000 lignes
* Entrepôt de données : Illimité

Ces limites s’appliquent aux rapports téléchargés et planifiés individuels. Les tableaux de bord sont limités au volume d’espace disponible au sein d’un petit rapport.

>[!NOTE] L’« heure de remise »/« heure de la journée » saisie par l’utilisateur indique l’heure à laquelle le traitement du rapport doit commencer et non pas l’heure à laquelle il sera livré. L’heure réelle à laquelle le rapport sera livré est principalement basée sur la durée du traitement (les rapports complexes et de grande taille ont un temps de traitement plus long que les rapports plus simples). Par exemple, si le traitement d’un rapport prend 15 minutes, alors l’heure de remise actuelle sera au moins 15 minutes après l’« heure de remise »/« heure de la journée » indiquée au départ.
>En outre, un certain nombre de facteurs peut contribuer à augmenter le retard avant la diffusion effective du rapport :
>
> * **L’exécution simultanée de nombreuses planifications du même type** (par exemple, plusieurs tableaux de bord, etc.) peut entraîner une surcharge du système. Le système de planification ne permet que l’exécution simultanée de quelques rapports (entre 5 et 10) d’un même type. Ainsi, si entre 5 et 10 rapports sont planifiés en même temps, certains devront attendre dans une file d’attente que les autres rapports soient terminés avant que leur traitement ne débute. Il est possible de limiter ce problème en planifiant les rapports d’une entreprise de manière échelonnée tout au long de la journée ou de l’heure, plutôt que simultanément.
> * En plus du type de rapport spécifique (Tableaux de bord, etc.), les rapports attendront également dans une file d’attente si l’entreprise a **plus de 15 à 20 rapports planifiés en même temps, quel que soit le type de rapports (parmi tous les types différents de rapports)**. Vous pouvez limiter ces délais en échelonnant les heures de planning au lieu plusieurs exécutions de rapports en même temps.
> * **Les problèmes sur les services en aval** sur lesquels le Planificateur compte peuvent également avoir des conséquences sur la diffusion des rapports. Par exemple, si vous utilisez indépendamment les API pour exécuter des rapports et remplir la file d’attente de requête API, alors la diffusion de vos rapports planifiés sera plus lente puisque les API sont en concurrence pour cette ressource.
> * **La latence de suite de rapports** (un retard dans la collecte de données) peut également retarder certains rapports planifiés.



## Envoi d’un rapport {#task_27642CD33D484FD0BF59EBD159EEF52C}

Cette section décrit la procédure à suivre pour télécharger des rapports et les envoyer par courrier électronique dans divers formats et pour planifier la remise d’un rapport. 

1. Run a report, then click **[!UICONTROL More]** > **[!UICONTROL Send]**.
1. Définissez les options de remise : 

   | Option | Description |
   |--- |--- |
   | Format | Sélectionnez PDF ou HTML. |
   | Envoyer à | Indiquez une adresse électronique pour recevoir le rapport. |
   | Sujet | Objet du courrier électronique. |
   | Planification | Sélectionnez cette option pour envoyer le rapport immédiatement ou à un autre intervalle. |

1. Cliquez sur **[!UICONTROL Advanced Delivery Options]** pour spécifier un planning de .

| Option | Description |
|--- |--- |
| Nom du fichier de rapport | Indique le nom du rapport. Le format par défaut est `<report name> for <suite> - <report date range>`. Pour spécifier un nom personnalisé, sélectionnez [!UICONTROL Custom]. |
| Format de rapport | Permet de spécifier les formats PDF, CSV, Excel, HTML, Word ou Mobile pour les  de. Si vous sélectionnez CSV, vous pouvez également spécifier le codage du fichier CSV :<ul><li>Shift-JIS : codage des caractères japonais.</li><li>EUC-JP : code Unix étendu, principalement pour le japonais, le coréen et le chinois simplifié.</li></ul> |
| Contenu du rapport | <ul><li>Nombre de lignes dans la table : définit le nombre de lignes visibles dans le tableau du rapport que vous envoyez.</li><li>Langue de l’en-tête et du pied de page : définit la langue de l’en-tête et du pied de page.</li><li>Commentaires : spécifie le texte qui apparaît au début du rapport.</li></ul> |
| Envoyer le fichier de signature numérique | Lorsque vous demandez un rapport, tel un rapport marqué ou des demandes de Data Warehouse, vous pouvez exiger une signature de données. La signature numérique d’Adobe ne limite pas l’accès aux données ; le fichier de signature numérique (.sig) a pour but de vérifier la validité du fichier de rapport remis. Grâce à la signature numérique, les de rapports peuvent vérifier que le fichier provient bien d’Adobe et qu’il n’a pas été modifié. |
| Destination du rapport | <ul><li>Courriel : vous permet de configurer l’adresse de courriel, l’objet et les remarques.</li><li>FTP : vous permet de configurer les paramètres FTP, notamment l’hôte, le port, le répertoire, le nom d’utilisateur et le mot de passe.</li></ul> |

1. Cliquez sur **[!UICONTROL Scheduling Options]**.

| Option | Description |
|--- |--- |
| Envoyer le rapport maintenant | Envoie le rapport immédiatement. |
| Planifier pour plus tard | Affiche les options permettant de spécifier une période et des options de  de. |
| Période du rapport | **Fixe** : empêche la date d’avancer au fil du temps. **Variable**: Permet à la date d’avancer au fil du temps. Quelques considérations :<ul><li>Si vous sélectionnez des dates de début et de fin variables et un rapport quotidien pour le jour précédent, vous recevrez chaque jour par courriel un rapport du jour précédent.</li><li>Si vous sélectionnez une date de début fixe et une date de fin variable, vous recevrez le premier jour un rapport pour le jour précédent. Le deuxième jour, vous recevrez un rapport pour les deux jours précédents ; le troisième jour, un rapport pour les trois jours précédents, etc.</li><li>Si vous sélectionnez des dates de début et de fin fixes, vous recevrez chaque jour un rapport identique pour les jours que vous avez définis.</li><li>Il n’est pas possible de sélectionner une date de début variable et une date de fin fixe.</li></ul> |
| Fréquence de remise de rapport | <ul><li>**Horaire**: envoie le courrier électronique toutes les heures, toutes les deux heures ou à tout autre intervalle horaire.</li><li>**Quotidien**: Envoie le courriel tous les jours, tous les deux jours, tous les trois jours ou à tout autre intervalle de jours. Vous pouvez également le faire envoyer tous les jours de la semaine.</li><li>**Hebdomadaire**: Envoie le courriel toutes les semaines, toutes les deux semaines, toutes les trois semaines ou à tout autre intervalle de semaines. Vous pouvez également spécifier le jour de la semaine où il est envoyé.</li><li>**Mensuel**: Indique l’intervalle en nombre de mois et vous pouvez également sélectionner le jour du mois où il est envoyé ou le jour de la semaine dans une semaine spécifique du mois.</li><li>**Annuel**: Indique le jour de l’année d’envoi du rapport ou vous pouvez envoyer le rapport un jour spécifique de la semaine dans n’importe quelle semaine de l’année.</li><li>**Heure du jour**: S’applique au fuseau horaire associé à la suite de rapports sélectionnée.</li></ul> |
| Options de remise | <ul><li>**Ne jamais finir**: Ne spécifie aucune fin.</li><li>**Expirer après`value` occurrences** : définit le nombre d’instances avant la fin de la remise.</li><li>**Expirer le** : vous permet de définir une date spécifique. Si vous souhaitez traiter les données le même jour que les données du rapport, le rapport contient uniquement les données qui ont été placées dans la base de données au moment de l&#39;envoi du rapport. Le traitement complet d’une journée pouvant prendre jusqu’à 24 heures, il se peut que des données complètes ne soient pas disponibles au moment de l’envoi du rapport. Pour des données complètes, définissez toujours le temps de traitement pendant 24 heures après la fin de la période de  du.</li></ul> |

## Impression d’un rapport {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Cette section décrit la procédure à suivre pour imprimer un rapport.

1. Exécutez un rapport.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Print]**.  ![](assets/print.png)

## Téléchargement d’un rapport à l’aide des options de base {#task_43660107A1C9485D92981CD75B562577}

Téléchargez des informations détaillées sur un rapport spécifique au format d’exportation de données PDF, CSV, Excel ou données brutes.

1. In  **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** , select a report to view.
1. Cliquez sur **[!UICONTROL Download]**.

   ![](assets/download_basic.png)

1. Sélectionnez le format de votre choix pour le rapport :

   * **[!UICONTROL PDF]** : le rapport sera téléchargé au format Adobe PDF. Vous pourrez ainsi le partager avec d’autres utilisateurs, quelle que soit leur plateforme informatique.
   * **[!UICONTROL CSV]** : le rapport sera téléchargé au format [!DNL .csv] (format de valeurs séparées par des virgules).
   * **[!UICONTROL Excel]**: Indique que le rapport sera téléchargé au format Microsoft Excel, ce qui vous permettra de le partager avec d’autres utilisateurs qui pourront l’ouvrir dans un de feuille de calcul.
   * **[!UICONTROL Word]**: Indique que le rapport sera téléchargé au format Microsoft Word.
   >[!NOTE]
   >
   >Si vous téléchargez un rapport dans l’un des formats d’exportation bruts et que le nom de la page est vierge, Adobe Analytics n’aura probablement pas le temps de traiter les données. Téléchargez le rapport ultérieurement.

## Gestion des rapports planifiés {#task_C17677C543454FF2B06D10EA5652DFBC}

Informations sur la gestion des rapports planifiés.

Dans [!UICONTROL Schedule Reports Manager], vous pouvez modifier et supprimer les  de rapports périodiques. Vous pouvez créer des planifications de  qui envoient vos rapports par courriel ou FTP à une adresse spécifiée. Vous pouvez configurer ces calendriers pour envoyer automatiquement les rapports à des intervalles spécifiés pendant une durée indéterminée ou indéfiniment, ou arrêter le  d’un rapport périodique.

The [!UICONTROL Schedule Report Manager] shows the items that a specific user has created. Si le compte d’utilisateur est désactivé dans l’application, toutes les livraisons planifiées sont interrompues.

1. Pour accéder au gestionnaire, cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Scheduled Reports]**.

## Partage d’un lien vers un rapport {#task_9711DDE9E140451B8C914EC5513E21EC}

Cette section décrit la procédure à suivre pour partager un rapport en générant un lien vers un rapport (URL) à envoyer à un autre utilisateur.

Lorsque le clique sur le lien, le système demande des informations d’identification de connexion (nom de l’, nom d’utilisateur et mot de passe). Une fois connecté, le affiche le rapport généré par l’utilisateur d’origine. Les restrictions d’autorisation standard s’appliquent.

**Pour partager un lien vers un rapport**

1. Exécutez un rapport.
1. Cliquez sur **[!UICONTROL More]** > **[!UICONTROL Link to This Report]**.

## Se désabonner des rapports planifiés {#concept_6B48360F935740B6851BA85D32DEF637}

Vous pouvez vous désabonner des rapports planifiés. Vous ne recevrez plus le rapport, même si votre nom d’utilisateur est rajouté au rapport planifié.

>[!IMPORTANT]
>
>Pour que vous puissiez de nouveau recevoir le rapport, une nouvelle planification doit être créée.

Pour vous désabonner d’un rapport planifié :

1. Affichez le courrier électronique avec le lien vers le rapport à partir duquel vous souhaitez vous désabonner.

   ![](assets/unsubscribe-email.png)

1. Cliquez sur le **[!UICONTROL click here]** lien en regard de **[!UICONTROL To cancel automatic delivery of this report]**.

1. Confirmez que vous souhaitez annuler le  du rapport.

   >[!NOTE]
   >
   >Ce processus est le même que vous soyez le planificateur ou le destinataire du rapport.

Le désabonnement d’un rapport n’annule pas le rapport planifié.

Pour annuler un rapport planifié, accédez au Gestionnaire de planification et cliquez sur le X rouge en regard du nom du rapport. [Plus...](/help/analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
