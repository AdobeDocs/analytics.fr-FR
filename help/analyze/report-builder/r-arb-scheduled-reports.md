---
description: Description des champs du Gestionnaire des tâches planifiées.
title: Gestionnaires des tâches planifiées
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
source-git-commit: 9a16f3942505028624e5c07568342a9acac898d7
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 43%

---

# Gestionnaires des tâches planifiées

Le [!UICONTROL Gestionnaire des tâches planifiées] vous permet d’afficher la liste des rapports planifiés existants, ainsi que leurs destinataires, les détails de planification et les formats de fichiers. Il vous permet également de réactiver les classeurs planifiés dont l’exécution a échoué.

## Suspension des tâches planifiées plus anciennes

Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans le Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications comprenaient la suppression de la possibilité que des diffusions planifiées &quot;se terminent après x occurrences&quot;. En réponse à plusieurs demandes de clients qui recherchent plus de temps pour explorer et mettre en oeuvre des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’à ce que **31 janvier 2023**.

Vous pourrez continuer à planifier les tâches de Report Builder horaire et les terminer au maximum après 99 occurrences. Notez que la restauration s’applique uniquement aux tâches horaires ; la &quot;fin après x occurrences&quot; reste indisponible pour tous les autres intervalles de diffusion (quotidiens, hebdomadaires, mensuels et annuels).

Cette option sera abandonnée le 31 janvier 2023.
Pour plus de questions ou d’assistance, contactez l’assistance clientèle Adobe.

Plus précisément, cette pause s’applique à **toutes les tâches créées avant le 31 janvier 2020 ;**. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé. Les tâches de plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée.

Toutes les tâches que vous souhaitez reprendre l’envoi peuvent être réactivées. Connectez-vous à Report Builder et lancez le [!UICONTROL Gestionnaire des tâches planifiées]. Cliquez sur **[!UICONTROL Réactiver]** pour la tâche planifiée que vous souhaitez reprendre l’envoi. Toute tâche qui sera réactivée aura une expiration par défaut de 18 mois, sauf si une date d’expiration plus courte est choisie.

En outre, toute tâche dont la date de création est inférieure à deux ans et dont la date d’expiration actuelle (ou dont la date d’expiration est supérieure à deux ans) sera appliquée à une date d’expiration de 18 mois par défaut. La nouvelle date d’expiration sera le 15 octobre 2023. Vous pouvez modifier cette date d’expiration pour qu’elle soit inférieure à 18 mois, mais pas supérieure. Au moment de l’expiration, la tâche sera suspendue. Vous pouvez toutefois réactiver la tâche avec une nouvelle date d’expiration de 18 mois. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé.

L’objectif de cette pause est de gérer et gérer efficacement notre base de données de tâches planifiées afin d’assurer des performances et une diffusion optimales pour les tâches et les classeurs nécessaires. Cela servira de nouvelle politique de gouvernance. Après le 31 janvier 2023, toutes les tâches auront une date d’expiration maximale de 18 mois. Au bout de 18 mois, les tâches expirées seront suspendues et pourront être réactivées si nécessaire.

## Configuration des tâches planifiées

| Champ | Description |
| --- | --- |
| Onglet **[!UICONTROL Rapports planifiés]** |  |
| [!UICONTROL Nom de rapport] | Indique le nom de la tâche planifiée. |
| [!UICONTROL Courriel/FTP] | Adresse e-mail ou FTP du destinataire. **Remarque :** si vous avez sélectionné Courriel, les rapports de plus de 1 Mo sont automatiquement joints sous forme de fichier .zip. Cette fonction évite que les pièces jointes ne soient trop volumineuses ; elle ne peut pas être désactivée. |
| [!UICONTROL Options de publication] | Cette colonne répertorie les Power BI si l’une des [Options de publication de Power BI](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/publish-powerbi/power-bi.html) est sélectionnée. |
| [!UICONTROL Planifier] | Type de la remise planifiée. |
| [!UICONTROL Format du fichier] | Format de remise du rapport, tel que Excel, PDF, HTML, etc. |
| [!UICONTROL Réactiver] | Si l’exécution d’un classeur planifié échoue, le Report Builder effectue deux tentatives d’exécution supplémentaires espacées de 15 minutes. Après trois tentatives infructueuses, le Report Builder désactive le planning et affiche le bouton Réactiver. Lorsque vous réactivez un classeur, la remise planifiée redémarre au niveau du point de désactivation.<p>Par exemple, si vous avez réactivé aujourd’hui un classeur planifié qui a été désactivé il y a 14 jours, il est exécuté et distribué 14 fois, soit 1 fois par jour de désactivation. Si vous ne souhaitez pas que la remise soit effectuée pour les jours manquants, vous pouvez supprimer le classeur planifié, puis en créer un nouveau en utilisant les mêmes paramètres de planification.<p>**Remarque :** Ne réactivez pas un classeur, sauf si vous connaissez le motif de sa désactivation. Pour résoudre les problèmes, téléchargez un classeur désactivé et actualisez-le du côté client. Si aucune erreur n’est détectée, vous devriez être en mesure de le réactiver. |
| [!UICONTROL Dernier envoi] | Date et heure auxquelles le rapport a été envoyé en dernier. |
| Onglet **Destinataire** |  |
| [!UICONTROL Courriel du destinataire] | Adresse e-mail du destinataire du rapport. |
| [!UICONTROL Rapports] | Rapports envoyés à chaque destinataire. |
| Onglet **Historique des rapports** |  |
| [!UICONTROL Nom de fichier] | Indique le nom de la tâche planifiée. |
| [!UICONTROL Date] | Date et heure auxquelles le rapport a été envoyé en dernier. |
| [!UICONTROL État] | L’état indique si le rapport a été Envoyé ou Pas envoyé. |
| [!UICONTROL Courriel/FTP] | Adresse e-mail ou FTP du destinataire du rapport. |
| [!UICONTROL Format du fichier] | Format de remise du rapport, tel que Excel, PDF, HTML, etc. |
