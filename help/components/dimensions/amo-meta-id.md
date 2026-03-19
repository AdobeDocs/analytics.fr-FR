---
title: ID de clic des méta-publicités AMO
description: L’identifiant de clic publicitaire Meta Adobe Media Optimizer, utilisé dans les intégrations Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# ID de clic des méta-publicités AMO

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
