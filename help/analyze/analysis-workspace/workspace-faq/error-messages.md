---
description: Découvrez les erreurs et la résolution des problèmes pour Analysis Workspace.
title: Erreurs et résolution des problèmes
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 100%

---

# Erreurs et résolution des problèmes

Vous pouvez rencontrer des erreurs lorsque vous interagissez avec Analysis Workspace qui peuvent affecter ses fonctionnalités ou ses performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

## Messages d’erreur

Certains messages d’erreur courants peuvent s’afficher lorsque vous utilisez Analysis Workspace :

| Message d’erreur | Pourquoi l’erreur se produit-elle ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL La suite de rapports fait l’objet de rapports exceptionnellement lourds. Veuillez réessayer ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée.<p>Les administrateurs et les administratrices peuvent utiliser le [Gestionnaire des activités de rapport pour identifier et annuler des requêtes](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) qui consomment de la capacité de création de rapports.</p> |
| [!UICONTROL Ce rapport est trop complexe. Veuillez consulter les bonnes pratiques pour créer des rapports Analysis Workspace.] | Votre requête de création de rapports est trop volumineuse et ne peut pas être exécutée. Les facteurs à l’origine de cette erreur sont les temporisations en raison de la complexité de la requête. | Simplifiez votre requête. Par exemple, raccourcissez la période, simplifiez les critères de segmentation ou supprimez certaines colonnes ou lignes de votre tableau. Vous pouvez également envisager de diviser le tableau en plusieurs requêtes distinctes. |
| [!UICONTROL La suite de rapports dépasse actuellement sa capacité de création de rapports. Simplifiez la demande ou réessayez ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les requêtes API, les projets planifiés, et les utilisateurs et les utilisatrices qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’assistance clientèle sous **[!UICONTROL Aide > Envoyer le ticket d’assistance]** en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Les problèmes liés à votre réseau local, tels que les [paramètres du pare-feu](/help/technotes/ip-addresses.md) de la société, sont un facteur contribuant à cette erreur. En outre, Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après quelques minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM à l’assistance clientèle. |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |


## Résolution des problèmes

Lorsque vous utilisez Analysis Workspace, vous pouvez utiliser les informations ci-dessous pour résoudre certains problèmes courants.

| Problème | Comment résoudre le problème |
|---|---|
| Lorsque je glisse et dépose une mesure, un message indique *Données non valides*. | Le message Données incorrectes signifie qu’Adobe ne peut pas renvoyer de données à l’aide de la combinaison de dimensions et de mesures utilisée dans le rapport. Par exemple, deux mesures empilées les unes sur les autres ne peuvent pas être renvoyées sous forme de données, car il n’est pas possible d’afficher deux mesures de cette manière. Placez plutôt les mesures côte à côte. |
| Lorsque je glisse et dépose une mesure, je ne vois aucune donnée, seulement des zéros. | Si vous avez réussi à créer un rapport Workspace, qui ne comporte cependant aucune donnée, vous pouvez effectuer quelques vérifications :<ul><li>Si vous avez appliqué un segment dans votre rapport, il se peut que les critères de segment ne correspondent à aucune donnée. Essayez de supprimer le segment ou d’ajuster la définition du segment.</li><li>Vérifiez la période dans le coin supérieur droit et pour vous assurer qu’elle est définie sur la valeur souhaitée.</li><li>Accédez à votre site Web et utilisez [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr) pour vérifier que la collecte des données s’effectue.</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/tools/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](/help/technotes/ip-addresses.md), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->