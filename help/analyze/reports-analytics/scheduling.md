---
description: Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.
seo-description: Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.
seo-title: Planification et distribution des rapports
solution: Analytics
subtopic: Planification
title: Planification et distribution des rapports
topic: Reports and Analytics
uuid: 1230 b 0 f 3-e 026-4 b 83-b 231-14 d 6 f 75 a 3836
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Planification et distribution des rapports

Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.

## Report schedule and distribution {#concept_4EA333DFC7FD4E9CA086385A3DA10BE9}

Cette section contient des informations sur la planification, le téléchargement et la distribution des rapports.

Lorsque vous planifiez la remise d’un rapport dans une application d’Adobe Analytics, vous pouvez utiliser les outils Planification et Diffusion pour afficher les fichiers qui ont été envoyés automatiquement et modifier ou interrompre les livraisons.

En raison des différences dans les mécanismes de traitement et les plateformes, les différents types de rapports planifiés et téléchargeables dans Adobe Analytics présentent différentes limites en ce qui concerne le nombre maximum de lignes qu’ils peuvent traiter dans une même requête. Voici les limites selon chaque type :

* Word, CSV, Excel, HTML et PDF : le même nombre de lignes visibles dans le rapport. Par défaut, cette limite est de 50 lignes mais peut atteindre les 200. Les rapports de ventilation ont une limite stricte de 50 lignes.
* Extractions des données : 50 000 lignes
* Data Warehouse : illimité

Notez que ces limites s’appliquent aux rapports téléchargés et planifiés individuels. Les tableaux de bord sont limités au volume d’espace disponible au sein d’un mini-rapport.

## Envoi d’un rapport {#task_27642CD33D484FD0BF59EBD159EEF52C}

Cette section décrit la procédure à suivre pour télécharger des rapports et les envoyer par courrier électronique dans divers formats et pour planifier la remise d’un rapport. 

<!-- 

t_send_report.xml

 -->

1. Run a report, then click **[!UICONTROL More]** &gt; **[!UICONTROL Send]**.
1. Définissez les options de remise : 

   | Option | Description |
   |--- |--- |
   | Format | Sélectionnez le format PDF ou HTML.. |
   | Envoyer à | Précisez une adresse de courriel où recevoir le rapport.. |
   | Sujet | Objet du courriel.. |
   | Planification | Choisissez d’envoyer le rapport immédiatement ou à un autre intervalle.. |

1. Click **[!UICONTROL Advanced Delivery Options]** to specify a delivery schedule.

   <table id="choicetable_2934E54FEE6E4D33B07EAC21F6DF628E"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Option </th> 
   <th class="chdeschd"> Description </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Nom de fichier du rapport</strong></td> 
   <td class="chdesc stentry"> <p>Spécifie le nom du rapport. Le format par défaut est le suivant : <code>&lt;nom du rapport&gt; pour &lt;suite&gt; - &lt;plage de dates du rapport&gt; </code>. </p> <p>Pour définir un nom personnalisé, sélectionnez <span class="uicontrol">Personnalisé </span>. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Format de rapport</strong></td> 
   <td class="chdesc stentry"> <p>Vous permet de définir les formats PDF, CSV, Excel, HTML, Word ou Mobile pour la remise. Si vous sélectionnez CSV, vous pouvez également définir le codage CSV : </p> <p> 
      <ul id="ul_4A2EB8D9512246589994052CF482BFD7"> 
      <li id="li_A4FC4D795A9D4F92AAB187ACDFBA180D"> <p> <span class="uicontrol"> Shift-JIS</span> : codage des caractères japonais. </p> </li> 
      <li id="li_405C7EC97F994D649A50F84466FADA3D"> <p> <span class="uicontrol"> EUC-JP</span> : code Unix étendu, principalement pour le japonais, le coréen et le chinois simplifié. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Contenu du rapport</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Nombre de lignes dans la table</span> : définit le nombre de lignes visibles dans le tableau du rapport que vous envoyez. </p> <p> <span class="uicontrol"> Langue de l’en-tête et du pied de page</span> : définit la langue de l’en-tête et du pied de page. </p> <p> <span class="uicontrol"> Commentaires</span> : spécifie le texte qui apparaît au début du rapport. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Envoyer le fichier de signature numérique</strong></td> 
   <td class="chdesc stentry"> <p>Lorsque vous demandez un rapport, tel un rapport marqué ou des demandes de Data Warehouse, vous pouvez exiger une signature de données. La signature numérique d’Adobe ne limite pas l’accès aux données ; le fichier de signature numérique (.sig) a pour but de vérifier la validité du fichier de rapport remis. Avec la signature numérique, les destinataires du rapport peuvent vérifier que le fichier provient bien d’Adobe et qu’il n’a pas été modifié. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Destination du rapport</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Courriel</span> : vous permet de configurer l’adresse de courriel, l’objet et les remarques. </p> <p> <span class="uicontrol"> FTP</span> : vous permet de configurer les paramètres FTP, notamment l’hôte, le port, le répertoire, le nom d’utilisateur et le mot de passe. </p> </td> 
   </tr> 
   </table>

1. Click **[!UICONTROL Scheduling Options]**.

   <table id="choicetable_589A39087F4C497D8913364FFF0125B7"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Option </th> 
   <th class="chdeschd"> Description </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Envoyer le rapport maintenant</strong></td> 
   <td class="chdesc stentry"> <p>Envoie immédiatement le rapport. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Le planifier pour plus tard</strong></td> 
   <td class="chdesc stentry"> <p>Affiche les options permettant de définir la période et les options de remise. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Période du rapport</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Fixe</span> : empêche la date d’avancer au fil du temps. </p> <p> <span class="uicontrol">Variable</span> : permet à la date d’avancer au fur et à mesure. Quelques considérations à prendre en compte : </p> <p> 
      <ul id="ul_5CDCCBEFEB364800A428614183A0E6A1"> 
      <li id="li_37B8F32A9E3B4979B5239A58F0C5A71C"> <p>Si vous sélectionnez des dates de début et de fin variables et un rapport quotidien pour le jour précédent, vous recevrez chaque jour par courriel un rapport du jour précédent. </p> </li> 
      <li id="li_83FFD2400C6A453783CDD9BB3B9BA3F9"> <p>Si vous sélectionnez une date de début fixe et une date de fin variable, vous recevrez le premier jour un rapport pour le jour précédent. Le deuxième jour, vous recevrez un rapport pour les deux jours précédents ; le troisième jour, un rapport pour les trois jours précédents, etc. </p> </li> 
      <li id="li_28F8552D699841BC942058247D39DBB9"> <p>Si vous sélectionnez des dates de début et de fin fixes, vous recevrez chaque jour un rapport identique pour le jour que vous avez défini. </p> </li> 
      <li id="li_A594A6E2A4044ED6AC0A80F88EB203B3"> <p>Il n’est pas possible de sélectionner une date de début variable et une date de fin fixe. </p> </li> 
      </ul> </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Fréquence de remise de rapport</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Par heure</span> : envoie le courriel chaque heure, une heure sur deux ou à tout autre intervalle horaire défini. </p> <p> <span class="uicontrol"> Quotidiennement</span> : envoie le courriel tous les jours, tous les deux jours, tous les trois jours ou à la fréquence définie. Vous pouvez également l’envoyer chaque jour de la semaine. </p> <p> <span class="uicontrol"> Hebdomadairement</span> : envoie le courriel toutes les semaines, toutes les deux semaines, toutes les trois semaines ou à la fréquence définie. Vous pouvez également définir un jour particulier de la semaine. </p> <p> <span class="uicontrol"> Mensuellement</span> : spécifie l’intervalle en nombre de mois. Vous pouvez également sélectionner un jour particulier du mois ou un jour spécifique d’une semaine du mois. </p> <p> <span class="uicontrol"> Annuellement</span> : indique un jour de l’année pour l’envoi du rapport. Vous pouvez également planifier l’envoi un jour d’une semaine spécifique dans l’année. </p> <p> <span class="uicontrol"> Heure</span> : s’applique au fuseau horaire associé à la suite de rapports sélectionnée. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Options de livraison</strong></td> 
   <td class="chdesc stentry"> <p> <span class="uicontrol"> Ne jamais expirer</span> : ne spécifie aucune fin. </p> <p> <span class="uicontrol"> Expirer après &lt;valeur&gt; occurrence(s)</span> : définit le nombre d’instances avant la remise. </p> <p> <span class="uicontrol"> Expirer le</span> : vous permet de définir une date spécifique. </p> <p>Si vous traitez les données le même jour que les données du rapport, le rapport contient uniquement les informations qui ont été ajoutées dans la base de données au moment de l’envoi du rapport. Le traitement complet d’une journée peut durer jusqu’à 24 heures. Il est par conséquent possible que l’intégralité des données ne soit pas disponible au moment de l’envoi du rapport. Pour que les données soient complètes, définissez toujours le délai de traitement pour 24 heures après l’expiration de la période de rapport. </p> </td> 
   </tr> 
   </table>

## Impression d’un rapport {#task_0F7CF6D6ED54462CAE4A793E271AF7E5}

Cette section décrit la procédure à suivre pour imprimer un rapport.

<!-- 

t_reports_print.xml

 -->

1. Exécution d’un rapport.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Print]**.  ![](assets/print.png)

## Téléchargement d’un rapport à l’aide des options de base {#task_43660107A1C9485D92981CD75B562577}

Téléchargez des informations détaillées sur un rapport spécifique au format d’exportation de données PDF, CSV, Excel ou données brutes.

<!-- 

t_download-report.xml

 -->

1. Sous **Analytics** &gt; **[!UICONTROL Rapports]**, sélectionnez un rapport à afficher.
1. Cliquez sur **[!UICONTROL Télécharger]**.

   ![](assets/download_basic.png)

1. Sélectionnez le format de votre choix pour le rapport :

   * **[!UICONTROL PDF]** : le rapport sera téléchargé au format Adobe PDF. Vous pourrez ainsi le partager avec d’autres utilisateurs, quelle que soit leur plate-forme informatique.
   * **[!UICONTROL CSV]**: Indique que le rapport sera téléchargé dans [!DNL .csv] (format de valeurs séparées par des virgules).
   * **[!UICONTROL Excel :]** le rapport sera téléchargé au format Microsoft Excel. Vous aurez ainsi la possibilité de le partager avec d’autres utilisateurs qui pourront l’ouvrir dans un tableur.
   * **[!UICONTROL Word]** : le rapport sera téléchargé au format Microsoft Word.
   >[!NOTE]
   >
   >Si vous utilisez l'un des formats d'exportation bruts pour télécharger un rapport et que le nom de la page est vide, Adobe Analytics n'a probablement pas suffisamment de temps pour traiter les données. Téléchargez le rapport ultérieurement.

## Gestion des rapports planifiés {#task_C17677C543454FF2B06D10EA5652DFBC}

Cette section contient des informations sur la gestion des rapports planifiés.

<!-- 

t_schedule_manage.xml

 -->

Dans le [!UICONTROL Gestionnaire de planification des rapports], vous pouvez modifier et supprimer les remises répétitives de rapports. Vous pouvez créer des calendriers de remise pour envoyer les rapports par courrier électronique ou FTP vers une adresse spécifiée. Vous pouvez configurer ces calendriers pour l’envoi automatique des rapports à des intervalles donnés pendant une période définie ou indéfiniment, ou arrêter la distribution d’un rapport récurrent.

Le [!UICONTROL Gestionnaire de planification des rapports] affiche les éléments créés par un utilisateur spécifique. Si le compte d’utilisateur est désactivé dans l’application, toutes les remises planifiées sont interrompues.

1. To access the manager, click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Scheduled Reports]**.

## Partage d’un lien vers un rapport {#task_9711DDE9E140451B8C914EC5513E21EC}

Cette section décrit la procédure à suivre pour partager un rapport en générant un lien (URL) vers ce rapport en vue de l’envoyer à un autre utilisateur.

<!-- 

t_reports_share_link.xml

 -->

Lorsque le destinataire clique sur le lien, le système demande les informations de connexion (nom de l’entreprise, nom d’utilisateur et mot de passe). Après identification, le destinataire voit s’afficher le rapport généré par l’utilisateur initial. Des restrictions d’autorisation standard s’appliquent.

**Pour partager un lien vers un rapport**

1. Exécution d’un rapport.
1. Click **[!UICONTROL More]** &gt; **[!UICONTROL Link to This Report]**.

## Se désabonner des rapports planifiés {#concept_6B48360F935740B6851BA85D32DEF637}

Vous pouvez vous désabonner des rapports planifiés. Vous ne recevrez plus le rapport même si votre nom d’utilisateur est de nouveau ajouté au rapport planifié.

<!-- 

t_schedule_unsubscribe.xml

 -->

>[!IMPORTANT]
>
>Pour que vous puissiez à nouveau recevoir le rapport, une nouvelle planification doit être créée.

Pour vous désabonner d’un rapport planifié :

1. Affichez l’e-mail avec le lien vers le rapport auquel vous souhaitez vous désabonner.

   ![](assets/unsubscribe-email.png)

1. Cliquez sur le lien **[!UICONTROL cliquez ici]** en regard de **[!UICONTROL Pour annuler la réception automatique de ce rapport]**.

1. Confirmez que vous souhaitez annuler l’envoi de ce rapport.

   >[!NOTE]
   >
   >Ce processus est le même que pour le planificateur du rapport ou le destinataire du rapport.

Le désabonnement d’un rapport n’annule pas le rapport planifié.

Pour annuler un rapport planifié, accédez au Gestionnaire de planification et cliquez sur le X rouge en regard du nom du rapport. [Plus…](../../analyze/reports-analytics/scheduling.md#task_C17677C543454FF2B06D10EA5652DFBC)
