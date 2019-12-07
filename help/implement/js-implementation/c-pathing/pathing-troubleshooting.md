---
description: Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.
keywords: Analytics Implementation
title: Raisons pour lesquelles le cheminement risque de ne pas être enregistré
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Raisons pour lesquelles le cheminement risque de ne pas être enregistré

Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.

* Le cheminement n’a pas été activé pour cette prop dans cette suite de rapports. Cette activation est spécifique à la suite de rapports.
* Les données ne sont pas transmises dans la prop correcte.
* Le cheminement a été activé et les données se trouvent dans la prop, mais elles ne s’affichent pas dans les rapports. Bien que les données [!UICONTROL sprop] puissent s’afficher dans les 10 minutes, les données de cheminement n’apparaissent pas tant que la session du visiteur n’est pas terminée. La fonctionnalité prend fin après 30 minutes d’inactivité. Il faut ensuite compter 10 minutes supplémentaires pour qu’Analytics termine le traitement des données de cheminement en vue de leur présentation finale dans des rapports.

Si les données ne s’affichent toujours pas alors que vous avez vérifié les points ci-dessus, contactez le service à la clientèle pour procéder à un débogage plus poussé.
