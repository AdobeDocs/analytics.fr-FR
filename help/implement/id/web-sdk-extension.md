---
title: Identification des visiteurs à l’aide de l’extension de balise Web SDK
description: Identifier correctement les visiteurs lors de l’implémentation de l’extension de balise Web SDK.
exl-id: 65de7fc3-a344-4f04-b523-1f5edf681d2f
TQID: 'https://experienceleague.adobe.com/4PVDioBDa-1VXg9Fpy0wA8-RZZYSXzVijj-b2kdEALQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: b3e5f43e-2e2f-43c0-810a-044a5f91e31a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 0%

---

# Identification des visiteurs à l’aide de l’extension de balise Web SDK

L’extension de balise Web SDK dans la collecte de données Adobe Experience Platform permet aux entreprises de mettre en œuvre le SDK Web à l’aide d’une interface de gestion des balises. Les scénarios avancés tels que le partage d’identifiants entre domaines et la migration de profils de visiteurs sont facilement configurés par le biais de règles et d’actions d’extension. L’utilisation de Web SDK permet de pérenniser votre implémentation et d’effectuer une mise à niveau transparente vers Customer Journey Analytics.

Les données d’identité peuvent être étendues pour prendre en charge les identifiants personnalisés et plusieurs espaces de noms à l’aide des [`identityMap`](https://experienceleague.adobe.com/fr/docs/experience-platform/collection/identity/identity-map) XDM. Adobe recommande d’utiliser l’ECID comme identifiant principal pour Analytics et d’utiliser d’autres options de gestion des identités pour les scénarios avancés.

Étant donné que le service d’identification des visiteurs est intégré nativement à l’extension de balise, il suffit de définir **[!UICONTROL Domaine]** à la valeur souhaitée. Si ce champ est défini correctement, l’identification des visiteurs fonctionne sans configuration supplémentaire.

>[!NOTE]
>
>N’incluez pas l’extension de balise du service d’identification des visiteurs si vous utilisez l’extension de balise Web SDK. L’extension du service d’identification des visiteurs n’est nécessaire que si vous utilisez l’extension [&#128279;](analytics-extension.md).
