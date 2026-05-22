---
title: AMO - ID de clic des publicités Meta
description: L’identifiant de clic publicitaire Meta Adobe Media Optimizer, utilisé dans les intégrations Adobe Advertising.
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 3%

---

# AMO - ID de clic des publicités Meta

L’**[!UICONTROL ID de clic publicitaire Meta AMO]** est un identifiant de clic publicitaire utilisé dans les intégrations Adobe Advertising. La dimension est automatiquement créée lors de l’activation de l’intégration [Analytics pour Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview). Il s’avère principalement utile en tant qu’identifiant de suivi brut plutôt qu’en tant que dimension de reporting lisible par l’utilisateur.

## Renseignement de cette dimension avec des données

Cette dimension collecte ses valeurs de plusieurs manières :

* Pour le trafic de clics publicitaires, les données sont collectées à partir du paramètre de chaîne de requête `fbclid` dans l’[URL de la page](page-url.md), généralement sur la page par laquelle le trafic piloté par les annonces accède au site.
* Le trafic de clics publicitaires peut également être capturé lorsque l’URL ne contient pas de codes de suivi, mais que le JavaScript Adobe Advertising détecte un clic au cours des deux minutes précédentes.

## Éléments de dimension

Les éléments Dimension incluent les identifiants de clics publicitaires générés par les réseaux publicitaires Meta (Facebook). La longueur de ces valeurs hachées peut varier, mais elle se compose généralement de centaines de caractères. Voici quelques exemples de valeurs (tronquées) :

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
