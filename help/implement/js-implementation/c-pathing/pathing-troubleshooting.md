---
description: Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.
keywords: Mise en œuvre d’Analytics
seo-description: Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.
seo-title: Raisons de l'enregistrement du cheminement
solution: Analytics
title: Raisons de l'enregistrement du cheminement
topic: Développeur et mise en œuvre
uuid: 9985 b 7 f 7-75 ea -4 c 94-97 a 3-520 f 92630989
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Raisons de l'enregistrement du cheminement

Liste des raisons pour lesquelles le cheminement risque de ne pas être enregistré et affiché dans les rapports.

* Le cheminement n’a pas été activé pour cette prop dans cette suite de rapports. Cette activation est spécifique à la suite de rapports.
* Les données ne sont pas transmises dans la prop correcte.
* Le cheminement a été activé et les données se trouvent dans la prop, mais elles ne s’affichent pas dans les rapports. Bien que les données [!UICONTROL sprop] puissent s’afficher dans les 10 minutes, les données de cheminement n’apparaissent pas tant que la session du visiteur n’est pas terminée. La fonctionnalité prend fin après 30 minutes d’inactivité. Il faut ensuite compter 10 minutes supplémentaires pour qu’Analytics termine le traitement des données de cheminement en vue de leur présentation finale dans des rapports.

Si les données ne s’affichent toujours pas alors que vous avez vérifié les points ci-dessus, contactez le service à la clientèle pour procéder à un débogage plus poussé.
