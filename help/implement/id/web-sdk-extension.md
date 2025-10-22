---
title: Identification des visiteurs à l’aide de l’extension de balise Web SDK
description: Identifier correctement les visiteurs lors de l’implémentation de l’extension de balise Web SDK.
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---

# Identification des visiteurs à l’aide de l’extension de balise Web SDK

L’extension de balise Web SDK dans la collecte de données Adobe Experience Platform permet aux entreprises de mettre en œuvre le SDK Web à l’aide d’une interface de gestion des balises. Les scénarios avancés tels que le partage d’identifiants entre domaines et la migration de profils de visiteurs sont facilement configurés par le biais de règles et d’actions d’extension. L’utilisation de Web SDK permet de pérenniser votre implémentation et d’effectuer une mise à niveau transparente vers Customer Journey Analytics.

Les données d’identité peuvent être étendues pour prendre en charge les identifiants personnalisés et plusieurs espaces de noms à l’aide des `identityMap` XDM. Adobe recommande d’utiliser le service Adobe Experience Cloud ID en tant qu’identifiant principal pour Analytics et d’utiliser d’autres options de gestion des identités pour les scénarios avancés.

Étant donné que le service d’identification des visiteurs est intégré nativement à l’extension de balise, il suffit de définir **[!UICONTROL Domaine Edge]** à la valeur souhaitée. Si ce champ est défini correctement, l’identification des visiteurs fonctionne sans configuration supplémentaire.

>[!NOTE]
>
>N’incluez pas l’extension de balise du service d’identification des visiteurs si vous utilisez l’extension de balise Web SDK. L’extension du service d’identification des visiteurs n’est nécessaire que si vous utilisez l’extension [Adobe Analytics](analytics-extension.md).
