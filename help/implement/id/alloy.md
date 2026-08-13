---
title: Identification des visiteurs à l'aide de la bibliothèque JavaScript Web SDK
description: Identifier correctement les visiteurs lors de l’implémentation de la bibliothèque JavaScript Web SDK.
exl-id: e650d6b1-6e29-4a9c-98dd-8482f50968d1
TQID: 'https://experienceleague.adobe.com/k9u260HKJg6hhs7REAQ3-uE4pHvrUPBv6x8yLjZ5tvc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 2%

---

# Identification des visiteurs à l&#39;aide de la bibliothèque JavaScript Web SDK

La bibliothèque Adobe Experience Platform Web SDK JavaScript (`alloy.js`) offre une approche unifiée et moderne de la collecte de données pour toutes les applications Adobe CX Enterprise, y compris Adobe Analytics. Bien que la plupart des clients implémentent généralement l’extension de balises [Web SDK](web-sdk-extension.md), vous pouvez utiliser la bibliothèque JavaScript Web SDK seule ou dans un système de gestion des balises tiers. Voir [Alloy](https://github.com/adobe/alloy) sur GitHub pour télécharger la dernière version de la bibliothèque.

Les données d’identité peuvent être étendues pour prendre en charge les identifiants personnalisés et plusieurs espaces de noms à l’aide des [`identityMap`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/identity-map) XDM. Adobe recommande d’utiliser l’ECID comme identifiant principal pour Analytics et d’utiliser d’autres options de gestion des identités pour les scénarios avancés.

Si votre entreprise utilise la bibliothèque JavaScript Web SDK pour envoyer des données à Adobe Analytics, une configuration minimale est requise pour l’identification des visiteurs. Le service Experience Platform Identity est intégré nativement à la bibliothèque, ce qui nécessite uniquement de définir le **[!UICONTROL domaine Edge]** dans la commande `configure`. Si ce champ est défini sur la valeur souhaitée, l’identification des visiteurs fonctionne sans configuration supplémentaire.
