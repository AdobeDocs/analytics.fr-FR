---
description: Découvrez la description des champs du Gestionnaire des tâches planifiées.
title: À propos du Gestionnaire des tâches planifiées
feature: Report Builder
role: User, Admin
exl-id: 8bacd7e4-ab50-4b36-842c-a8b6130a58d9
TQID: https://experienceleague.adobe.com/bH-sAinp0Hf0X9qesfrJMIUYdDqjrev5Hd7mRpihDLM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 788
ht-degree: 21%

---

# Gestionnaires des tâches planifiées

{{legacy-arb}}

Le [!UICONTROL Gestionnaire des tâches planifiées] vous permet d’afficher une liste des rapports planifiés existants, ainsi que leurs destinataires, les détails du planning et les formats de fichiers. Il vous permet également de réactiver les classeurs planifiés dont l’exécution a échoué.

## Suspension des anciennes tâches planifiées

Le 21 avril 2022, nous avons apporté des modifications aux tâches planifiées dans Report Builder dans le cadre de nos efforts d’optimisation des performances et des diffusions. Ces modifications ne permettaient plus que les diffusions planifiées se terminent « après x occurrences ». En réponse à plusieurs demandes de clients souhaitant disposer de plus de temps pour explorer et implémenter des alternatives, nous avons décidé de restaurer cette option de manière limitée jusqu’au **31 janvier 2023**.

Vous pourrez toujours planifier des tâches Report Builder horaires et faire en sorte qu’elles se terminent après un maximum de 99 occurrences. Veuillez noter que la restauration ne s’applique qu’aux tâches horaires ; l’option « se terminent après x occurrences » restera indisponible pour tous les autres intervalles de diffusion (quotidien, hebdomadaire, mensuel et annuel).

Veuillez noter que cette option est supprimée à compter du 31 janvier 2023.
Pour toute question ou assistance, contactez l’Assistance clientèle d’Adobe.

Plus précisément, cette pause s’applique à **toutes les tâches créées avant le 31 janvier 2020**. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé. Les tâches de plus de deux ans seront suspendues et aucune autre tâche planifiée ne sera envoyée.

Toutes les tâches que vous souhaitez reprendre à envoyer peuvent être réactivées. Connectez-vous à Report Builder et lancez le [!UICONTROL Gestionnaire des tâches planifiées]. Cliquez sur **[!UICONTROL Réactiver]** pour la tâche planifiée que vous souhaitez reprendre à envoyer. Toute tâche réactivée aura une expiration par défaut de 18 mois, sauf si une date d’expiration plus courte est choisie.

En outre, toute tâche dont la date de création est inférieure à deux ans, et qui n’a pas de date d’expiration actuelle (ou dont la date d’expiration est supérieure à deux ans) se verra appliquer une date d’expiration par défaut de 18 mois. La nouvelle date d’expiration est le lundi 15 octobre 2023. Vous pouvez modifier cette date d’expiration pour qu’elle soit inférieure à 18 mois, mais pas supérieure. Au moment de l’expiration, la tâche est en pause. Cependant, vous pouvez réactiver la tâche avec une nouvelle date d’expiration de 18 mois. Aucune tâche, aucun classeur ni aucune donnée ne sera supprimé.

Cette pause a pour but de gérer et de gérer efficacement notre base de données de tâches planifiées afin d’assurer des performances et une diffusion optimales pour les tâches et les classeurs nécessaires. Cela constituera notre nouvelle politique en matière de gouvernance. Après le 31 janvier 2023, toutes les tâches auront une date d’expiration maximale de 18 mois. Au bout de 18 mois, les tâches expirées seront suspendues et pourront être réactivées si nécessaire.

## Configuration des tâches planifiées

| Champ | Description |
| --- | --- |
| **[!UICONTROL Onglet Rapports planifiés]** | |
| [!UICONTROL Nom du rapport] | Indique le nom de la tâche planifiée. |
| [!UICONTROL  E-mail/FTP ] | Adresse e-mail ou FTP du destinataire. **Remarque :** si vous sélectionnez l’option E-mail, les rapports de plus de 1 Mo sont automatiquement joints à l’e-mail sous la forme d’un fichier .zip. Cette fonction évite que les pièces jointes ne soient trop volumineuses ; elle ne peut pas être désactivée. |
| [!UICONTROL Options de publication] | Cette colonne répertorie Power BI si l’une des [options de publication Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) est sélectionnée. |
| [!UICONTROL Planning] | Type de diffusion planifiée. |
| [!UICONTROL Format de fichier] | Format de diffusion du rapport, tel qu’Excel, PDF, HTML, etc. |
| [!UICONTROL Réactiver] | Si l’exécution d’un classeur planifié échoue, le Report Builder effectue deux tentatives d’exécution supplémentaires espacées de 15 minutes. Après trois échecs de tentative, Report Builder désactive le planning et affiche le bouton Réactiver . Lorsque vous réactivez un classeur, la diffusion planifiée redémarre à partir du moment où elle a été désactivée.<p>Par exemple, si un classeur planifié a été désactivé il y a 14 jours et que vous le réactivez aujourd’hui, il s’exécute pour chaque jour manquant et est distribué 14 fois. Si vous ne souhaitez pas que le classeur soit livré pendant les jours manquants, vous pouvez supprimer le classeur planifié, puis en créer un autre en utilisant les mêmes paramètres de planification.<p>**Remarque :** ne réactivez pas un classeur à moins de connaître la raison pour laquelle le système l’a désactivé. Pour résoudre le problème, téléchargez un classeur désactivé et actualisez-le côté client. Si aucune erreur ne s’affiche, vous devriez être en mesure de la réactiver. |
| [!UICONTROL Dernier envoi] | Date et heure du dernier envoi du rapport. |
| **Onglet Destinataire** | |
| [!UICONTROL Email du destinataire] | Adresse e-mail du destinataire du rapport. |
| [!UICONTROL Rapports] | Rapports envoyés à chaque destinataire. |
| **Onglet Historique des rapports** | |
| [!UICONTROL Nom du fichier] | Indique le nom de la tâche planifiée. |
| [!UICONTROL Date] | Date et heure du dernier envoi du rapport. |
| [!UICONTROL Statut] | Le statut indique si le rapport a été envoyé ou non. |
| [!UICONTROL  E-mail/FTP ] | Adresse e-mail ou FTP du destinataire du rapport. |
| [!UICONTROL Format de fichier] | Format de diffusion du rapport, tel qu’Excel, PDF, HTML, etc. |
