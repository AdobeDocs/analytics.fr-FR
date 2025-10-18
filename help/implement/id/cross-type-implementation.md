---
title: Suivi sur différents types de mises en œuvre
description: Utilisez différents types de mise en œuvre et effectuez un suivi transparent des visiteurs entre eux.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 64%

---

# Suivi sur différents types de mises en œuvre

L’architecture principale d’une implémentation Adobe Analytics est cohérente pour tous les types d’implémentation. Le processus implique de définir des variables et de les compiler dans une demande d’image envoyée aux serveurs de collecte de données d’Adobe. Ce concept signifie que vous pouvez basculer facilement entre AppMeasurement, le SDK Web et leurs extensions respectives dans la collecte de données Adobe Experience Platform sur différentes pages du même site.

Adobe recommande de maintenir une cohérence sur l’ensemble de l’implémentation d’un site en utilisant le même type d’implémentation sur toutes les pages. Cependant, si des parties de votre site ont des exigences différentes, vous pouvez utiliser cette page pour vous assurer que le suivi des visiteurs et visiteuses est cohérent entre les pages.

Si vous utilisez plusieurs types d’implémentation (des demandes d’image codées en dur et AppMeasurement, par exemple), assurez-vous que les variables suivantes sont correctement définies et qu’elles correspondent.

>[!NOTE]
>
>Tous les types d’implémentation doivent utiliser le même type d’identification des visiteurs (Analytics ID hérité ou Visitor ID Service). Adobe recommande d’utiliser le service d’identification des visiteurs dans toutes les implémentations lorsque cela est possible.

| Variable | AppMeasurement | Extension Analytics | Web SDK (Alloy) | Extension de balises du SDK Web | Demande d’image codée en dur |
| --- | --- | --- | --- | --- | --- |
| Identifiant de suite de rapports | Argument de chaîne en [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Suites de rapports] sous la section [!UICONTROL Gestion des bibliothèques] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=fr) | Ajouter Adobe Analytics en tant que service lors de la [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr) | Ajouter Adobe Analytics en tant que service lors de la [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr) | Partie de l’URL `pathname` (après `/b/ss/`) |
| Service Experience Cloud ID | Mise en œuvre [`VisitorAPI.js`](appmeasurement.md) | Utilisez l’extension du service Experience Cloud ID [](analytics-extension.md) | [ Inclus nativement ](alloy.md) | [ Inclus nativement ](web-sdk-extension.md) | Effectuez un [appel distinct au service d’ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=fr) pour obtenir l’identifiant souhaité et inclure l’`mid` dans la chaîne de requête |
| domaine Edge | La variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Serveur de suivi SSL] dans la section [!UICONTROL Général] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=fr) | La propriété `edgeDomain` lors de la [Configuration du SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) | Le champ [!UICONTROL Domaine Edge] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=fr) | Le `hostname` de l’URL de demande d’image |

Si l’une de ces variables n’est pas cohérente pour chaque type d’implémentation, Adobe les considère comme des visiteurs et visiteuses distincts. Si le suivi des visiteurs et visiteuses n’est pas effectué de manière transparente sur les types d’implémentation de votre site, la raison la plus courante est que l’ID Service est mal configuré. Assurez-vous que chaque type d’implémentation obtient correctement le même Experience Cloud ID (`mid`) sur l’ensemble de votre site.
