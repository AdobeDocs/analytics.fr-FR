---
description: Lorsque vous planifiez un rapport, vous pouvez choisir un de publication à utiliser pour la distribution.
title: Autoriser les remplacements de la liste de publication
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Autoriser les remplacements de la liste de publication

Lorsque vous planifiez un rapport, vous pouvez choisir un de publication à utiliser pour la distribution.

Les  de publication sont configurées dans les outils d’administration d’Analytics.

Voir [Publication du Gestionnaire](https://marketing.adobe.com/resources/help/fr_FR/reference/publishing_list.html) de publication dans la référence Analytics.

Pour activer cette fonctionnalité, accédez à la [!UICONTROL Request Wizard: Step 1] fenêtre.

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. En outre, si le classeur contient plusieurs suites de rapports, l’identifiant de suite de rapports associé au de publication est utilisé.

Cette option n’est pas disponible pour les suites de rapports que vous sélectionnez dans les cellules.

>[!NOTE] Si vous envoyez le rapport planifié à plusieurs listes de publication, il s’exécute une fois pour chaque liste. Les suites de rapports variables sont remplacées par celle qui est affectée à la liste de publication.

