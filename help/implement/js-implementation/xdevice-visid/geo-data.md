---
description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
keywords: Mise en œuvre d’Analytics
seo-description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
seo-title: Données de géosegmentation
solution: Analytics
title: Données de géosegmentation
topic: Développeur et mise en œuvre
uuid: 8449 bf 11-c 367-4698-a 73 e-f 6 cb 59 f 8 c 945
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Données de géosegmentation

>[!IMPORTANT]
>
>Cette méthode d'identification des visiteurs sur l'ensemble des périphériques n'est plus recommandée. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.

Si un utilisateur consulte votre site à partir de son ordinateur privé, puis à partir d’un périphérique mobile (dans les 30 minutes), les données de géosegmentation ne changent pas. Si vous utilisez VISTA pour renseigner une evar avec des données de géosegmentation, elle est basée sur l'adresse IP de chaque accès. Cela peut entraîner plusieurs valeurs de données de géosegmentation si l'adresse IP change pour la même visite.
