---
description: Liste des messages d’erreur d’Adobe Analysis Workspace et ses composants connexes
title: Messages d’erreur courants dans Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 6412fc0027c84df3b02ef2e7cbf35d24b4ee9319
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 100%

---

# Messages d’erreur courants

Vous pouvez rencontrer des erreurs lors de l’interaction avec Analysis Workspace qui influenceront également les performances. Les types d’erreur les plus courants sont répertoriés ci-dessous, ainsi que les raisons pour lesquelles ils se produisent et les optimisations qui peuvent être effectuées.

| Message d’erreur | Quelle en est la raison ? | Optimisation |
| --- | --- | --- |
| [!UICONTROL La suite de rapports fait l’objet de rapports exceptionnellement lourds. Veuillez réessayer ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. |
| [!UICONTROL La suite de rapports dépasse actuellement sa capacité de création de rapports. Simplifiez la demande ou réessayez ultérieurement.] | Votre entreprise essaie d’exécuter trop de requêtes simultanées sur une suite de rapports spécifique. Les facteurs à l’origine de cette erreur sont les demandes d’API, les projets planifiés, les rapports planifiés, les alertes planifiées et les utilisateurs qui effectuent simultanément des demandes de création de rapports. | Diffusez vos requêtes et plannings pour la suite de rapports de manière plus uniforme tout au long de la journée. |
| [!UICONTROL Une erreur système s’est produite. Veuillez soumettre un ticket à l’Assistance clientèle sous Aide > Envoyer le ticket d’assistance en incluant votre code d’erreur.] | Adobe rencontre un problème qui doit être résolu. | Envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Une erreur inattendue s’est produite ; essayez de réactualiser votre projet. Si le problème persiste, envoyez cet identifiant d’erreur à l’Assistance clientèle d’Adobe pour obtenir un diagnostic plus précis.] | Adobe rencontre un problème qui doit être résolu. | Essayez d’actualiser votre projet et si le problème persiste, envoyez le code d’erreur à l’Assistance clientèle. |
| [!UICONTROL Erreur 500 : Échec du chargement de la page] | Les problèmes liés à votre réseau local, tels que les [paramètres du pare-feu](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html?lang=fr) de la société, sont un facteur contribuant à cette erreur. En outre, Adobe peut rencontrer un problème qui doit être résolu. | Essayez de vous reconnecter après quelques minutes. Si le problème persiste, envoyez le code d’ID d’instance EIM à l’assistance clientèle. |
| [!UICONTROL L’un des segments ou la recherche dans cette visualisation contient une recherche de texte qui a renvoyé trop de résultats.] | Les critères de segment ou le filtre de rapport sont trop étendus. | Limitez vos critères de texte de recherche et effectuez une nouvelle requête. |
| [!UICONTROL Actuellement, cette dimension ne prend pas en charge les modèles d’attribution autres que ceux par défaut.] | L’attribution autre que par défaut n’est pas prise en charge pour la dimension que vous utilisez. | Remplacez la dimension de votre tableau par une dimension compatible avec [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Votre requête a échoué en raison d’un trop grand nombre de colonnes ou de lignes préconfigurées.] | Votre tableau comporte trop de cellules à structure libre (ligne * colonnes). | Supprimez les colonnes ou les lignes du tableau ou envisagez de diviser le tableau en requêtes distinctes. |
