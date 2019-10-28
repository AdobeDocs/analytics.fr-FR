---
description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
keywords: Mise en œuvre d’Analytics
seo-description: Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.
seo-title: Données de géosegmentation
solution: Analytics
title: Données de géosegmentation
topic: Développeur et mise en œuvre
uuid: 8449bf11-c367-4698-a73e-f6cb59f8c945
translation-type: ht
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Données de géosegmentation

>[!IMPORTANT]
>
>Cette méthode d’identification des visiteurs sur plusieurs appareils n’est plus recommandée. Reportez-vous à la [documentation d’Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/fr_FR/mcdc/).

Les données de géosegmentation sont enregistrées selon le premier accès de la visite. Elles ne changent pas pour une même visite, quel que soit le périphérique utilisé.

Si un utilisateur consulte votre site à partir de son ordinateur privé, puis à partir d’un périphérique mobile (dans les 30 minutes), les données de géosegmentation ne changent pas. Si vous utilisez VISTA pour renseigner des données de géosegmentation dans une eVar, elles sont basées sur l’adresse IP de chaque accès. Cela peut se traduire par un grand nombre de valeurs de données de géosegmentation si l’adresse IP change pour une même visite.
