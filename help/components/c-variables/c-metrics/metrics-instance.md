---
description: Nombre de fois où une valeur a été définie pour une variable.
keywords: instances
seo-description: Nombre de fois où une valeur a été définie pour une variable.
seo-title: Instances
solution: Analytics
title: Instances
topic: Mesures
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Instances

Nombre de fois où une valeur a été définie pour une variable.

Les instances sont comptabilisées pour tous les types d’accès mais ne sont pas comptabilisées lorsqu’une valeur est enregistrée pour une variable sur un accès suivant en raison de la persistance.

For example, if a user arrives on your site via [!DNL example.com], the first image request on your site contains the referrer of [!DNL example.com]. When this value is set, one Instance is attributed to [!DNL example.com] even though this referrer is recorded for all pages viewed during that visit.

Les instances relatives aux variables de conversion de Data Warehouse ont été ajoutées à la mi-2011, permettant ainsi aux demandes de Data Warehouse de traiter une instance de variable de conversion spécifique comme une mesure. Ces mesures ne sont pas disponibles à des fins de création de rapports avant la date de leur introduction.
