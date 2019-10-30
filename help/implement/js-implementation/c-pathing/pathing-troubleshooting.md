---
description: Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.
keywords: Mise en œuvre d’Analytics
seo-description: Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.
seo-title: Raisons pour lesquelles le cheminement risque de ne pas être enregistré
solution: Analytics
title: Raisons pour lesquelles le cheminement risque de ne pas être enregistré
topic: Développeur et mise en œuvre
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Raisons pour lesquelles le cheminement risque de ne pas être enregistré

Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.

* Le cheminement n’a pas été activé pour cette prop dans cette suite de rapports. Cette activation est spécifique à la suite de rapports.
* Les données ne sont pas transmises dans la prop correcte.
* Le cheminement a été activé et les données se trouvent dans la prop, mais elles ne s’affichent pas dans les rapports. Bien que les données [!UICONTROL sprop] puissent s’afficher dans les 10 minutes, les données de cheminement n’apparaissent pas tant que la session du visiteur n’est pas terminée. La fonctionnalité prend fin après 30 minutes d’inactivité. Il faut ensuite compter 10 minutes supplémentaires pour qu’Analytics termine le traitement des données de cheminement en vue de leur présentation finale dans des rapports.

Si les données ne s’affichent toujours pas alors que vous avez vérifié les points ci-dessus, contactez le service à la clientèle pour procéder à un débogage plus poussé.
