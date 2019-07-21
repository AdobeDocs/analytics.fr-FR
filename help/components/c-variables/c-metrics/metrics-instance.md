---
description: Nombre de fois où une valeur a été définie pour une variable.
keywords: instances
seo-description: Nombre de fois où une valeur a été définie pour une variable.
seo-title: Instances
solution: Analytics
title: Instances
topic: Mesures
uuid: fec 94 bdd-a 1 dc -4 cb 0-8983-ea 575 b 69589 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Instances

Nombre de fois où une valeur a été définie pour une variable.

Les instances sont comptabilisées pour tous les types d’accès mais ne sont pas comptabilisées lorsqu’une valeur est enregistrée pour une variable sur un accès suivant en raison de la persistance.

For example, if a user arrives on your site via [!DNL example.com], the first image request on your site contains the referrer of [!DNL example.com]. When this value is set, one Instance is attributed to [!DNL example.com] even though this referrer is recorded for all pages viewed during that visit.

Les instances relatives aux variables de conversion de Data Warehouse ont été ajoutées à la mi-2011, permettant ainsi aux demandes de Data Warehouse de traiter une instance de variable de conversion spécifique comme une mesure. Ces mesures ne sont pas disponibles à des fins de création de rapports avant la date de leur introduction.
