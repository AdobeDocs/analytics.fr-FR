---
description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
keywords: Mise en œuvre d’Analytics
seo-description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
seo-title: Données de géosegmentation
solution: Analytics
title: Données de géosegmentation
topic: Développeur et mise en œuvre
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Données de géosegmentation

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la documentation [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.

Si un utilisateur consulte votre site à partir de son ordinateur privé, puis à partir d’un périphérique mobile (dans les 30 minutes), les données de géosegmentation ne changent pas. Si vous utilisez VISTA pour renseigner des données de géosegmentation dans une eVar, elles sont basées sur l’adresse IP de chaque accès. Cela peut se traduire par un grand nombre de valeurs de données de géosegmentation si l’adresse IP change pour une même visite.
