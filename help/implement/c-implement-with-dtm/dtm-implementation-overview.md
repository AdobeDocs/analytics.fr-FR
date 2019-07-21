---
description: valeur nulle
keywords: Implémentation d'Analytics ; implementation method ; gestion dynamique des balises ; dtm
seo-description: valeur nulle
seo-title: Présentation de l'implémentation de la gestion dynamique des balises
solution: Analytics
title: Présentation de l'implémentation de la gestion dynamique des balises
topic: Développeur et mise en œuvre
uuid: 2 d 40 cb 7 a -5 c 69-4 f 41-81 a 7-c 48373 c 2 d 720
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Présentation de l'implémentation de la gestion dynamique des balises

Utilisez Dynamic Tag Management pour gérer les balises de même que collecter et distribuer des données à travers les systèmes de marketing numérique. Dynamic Tag Management procure une couche de données unique qui pousse les données à partir de plusieurs sources. Elle permet également une diffusion réactive du contenu spécifique à un utilisateur.

Cette section d’aide fournit des informations spécifiques sur l’utilisation de Dynamic Tag Management pour mettre en œuvre Adobe Analytics. Pour des informations détaillées sur Dynamic Tag Management, consultez la [documentation du produit de Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/dtm/). Pour plus d’informations sur l’accès à Dynamic Tag Management et les tâches courantes lorsque vous commencez à l’utiliser, voir [Prise en main](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) dans la documentation du produit de Dynamic Tag Management.

Pour un résumé détaillé des étapes de mise en œuvre de Dynamic Tag Management, consultez [Déploiement d’Adobe Analytics avec Dynamic Tag Management](https://marketing.adobe.com/resources/help/en_US/analytics/getting-started/add-adobe-analytics-dtm-tool.html) dans Prise en main d’Adobe Analytics.

## Vue d’ensemble des étapes de mise en œuvre {#section_D0BBB82486F44699AC7FF5E76E27434C}

Ce guide vous présente les étapes suivantes de mise en œuvre d’Analytics avec la gestion dynamique des balises :

1. [Création d’une propriété web](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123).
1. [Configuration des options d’hébergement](../../implement/c-implement-with-dtm/t-configure-hosting.md#task_EAD99BB391F544C0BB197D0B3D03EBAC).
1. [Ajout du code d’en-tête et de pied de page à chaque page gérée](../../implement/c-implement-with-dtm/c-headers-footers/t-header-footer-code.md#task_43C8DD699A514638B0620775C06423E5).
1. [Ajout de l’outil Adobe Analytics](../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8).
1. Create [data elements](../../implement/c-implement-with-dtm/t-data-element.md#task_962EF08CE2AE49B3B739295F6E4792C2), [rules and conditions](../../implement/c-implement-with-dtm/c-rules/t-rules-create.md#task_B7FB5ED415AF430C952265AC2835C0DB), and [actions](../../implement/c-implement-with-dtm/c-rules/t-rules-actions.md#task_94DFE0D8B53A43E2892851BABE381121).

1. Publication des outils et des règles sur le serveur de production.

