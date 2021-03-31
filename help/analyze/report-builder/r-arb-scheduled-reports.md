---
description: Description des champs du Gestionnaire des tâches planifiées.
title: Gestionnaires des tâches planifiées
uuid: dec259f0-2a04-4c94-abbc-5008cf2f1cb8
feature: Report Builder
role: Professionnel, Administrateur
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 97%

---


# Gestionnaires des tâches planifiées

Le Gestionnaire des tâches planifiées vous permet d’afficher une liste des rapports planifiés existants, ainsi que leurs destinataires, les détails de la planification et les formats de fichier. Il vous permet également de réactiver les classeurs planifiés dont l’exécution a échoué.

| Champ | Description |
| --- | --- |
| Onglet **Rapports planifiés** |  |
| Nom de rapport | Indique le nom de la tâche planifiée. |
| Courriel/FTP | Adresse électronique ou FTP du destinataire. **Remarque :** si vous avez sélectionné Courriel, les rapports de plus de 1 Mo sont automatiquement joints sous forme de fichier .zip. Cette fonction évite que les pièces jointes ne soient trop volumineuses ; elle ne peut pas être désactivée. |
| Options de publication | Cette colonne contient Power BI si l’une des [options de publication Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) est sélectionnée. |
| Planifier | Type de la remise planifiée. |
| Format du fichier | Format de remise du rapport, tel que Excel, PDF, HTML, etc. |
| Réactiver | Si l’exécution d’un classeur planifié échoue, le Report Builder effectue deux tentatives d’exécution supplémentaires espacées de 15 minutes. Après trois tentatives infructueuses, le Report Builder désactive le planning et affiche le bouton Réactiver. Lorsque vous réactivez un classeur, la remise planifiée redémarre au niveau du point de désactivation.  Par exemple, si vous avez réactivé aujourd’hui un classeur planifié qui a été désactivé il y a 14 jours, il est exécuté et distribué 14 fois, soit 1 fois par jour de désactivation. Si vous ne souhaitez pas que la remise soit effectuée pour les jours manquants, vous pouvez supprimer le classeur planifié, puis en créer un nouveau en utilisant les mêmes paramètres de planification.   Remarque : il est déconseillé de réactiver un classeur, sauf si vous connaissez le motif de sa désactivation. Une méthode de dépannage consiste à télécharger un classeur désactivé, puis à l’actualiser sur le client. Si aucune erreur n’est détectée, vous devriez être en mesure de le réactiver. |
| Dernier envoi | Date et heure auxquelles le rapport a été envoyé en dernier. |
| Onglet **Destinataire** |  |
| Courriel du destinataire | Adresse électronique du destinataire du rapport. |
| Rapports | Le ou les rapports qui ont été envoyés à chaque destinataire. |
| Onglet **Historique des rapports** |  |
| Nom de fichier | Indique le nom de la tâche planifiée. |
| Date | Date et heure auxquelles le rapport a été envoyé en dernier. |
| État | L’état indique si le rapport a été Envoyé ou Pas envoyé. |
| Courriel/FTP | Adresse électronique ou FTP du destinataire du rapport. |
| Format du fichier | Format de remise du rapport, tel que Excel, PDF, HTML, etc. |

