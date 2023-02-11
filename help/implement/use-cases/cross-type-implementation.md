---
title: Suivi sur différents types de mises en œuvre
description: Utilisez différents types de mise en œuvre et effectuez un suivi transparent des visiteurs entre eux.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 18%

---

# Suivi sur différents types de mises en œuvre

L’architecture principale d’une mise en oeuvre Adobe Analytics est cohérente pour tous les types de mise en oeuvre. Le processus implique de définir des variables et de les compiler dans une demande d’image envoyée aux serveurs de collecte de données d’Adobe. Ce concept signifie que vous pouvez basculer facilement entre AppMeasurement, le SDK Web et leurs extensions respectives dans la collecte de données Adobe Experience Platform sur différentes pages du même site.

Adobe recommande de maintenir la cohérence entre l’implémentation d’un site en utilisant le même type d’implémentation sur toutes les pages. Cependant, si des parties de votre site ont des exigences différentes, vous pouvez utiliser cette page pour vous assurer que les visiteurs sont suivis de manière cohérente entre les pages.

Si vous utilisez plusieurs types de mise en oeuvre (comme AppMeasurement et les demandes d’image codées en dur), assurez-vous que les variables suivantes sont correctement définies et correspondent :

| Variable | AppMeasurement | Extension Analytics | SDK Web | Extension SDK web | Demande d’image codée en dur |
| --- | --- | --- | --- | --- | --- |
| Identifiant de suite de rapports | Argument de chaîne dans [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Suites de rapports] sous le [!UICONTROL Gestion des bibliothèques] lors de la section [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Ajoutez Adobe Analytics en tant que service lorsque [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr) | Ajoutez Adobe Analytics en tant que service lorsque [Configuration d’un flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr) | Partie de l’URL `pathname` (après `/b/ss/`) |
| Serveur de suivi | Le [`trackingServer`](../vars/config-vars/trackingserver.md) et [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variables | [!UICONTROL Serveur de suivi] et [!UICONTROL Serveur de suivi SSL] sous le [!UICONTROL Général] lors de la section [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Le `edgeDomain` lorsque [Configuration du SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=fr) | Le [!UICONTROL Domaine Edge] when [Configuration de l’extension](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=fr) | Le `hostname` de l’URL de demande d’image |
| Service Experience Cloud ID | Mise en œuvre [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=fr) | Utilisez la variable [Extension du service Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilisez la variable [Extension du service Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilisez la variable [Extension du service Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Effectuez une [appel distinct aux serveurs du service d’ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) pour obtenir l’identifiant souhaité |

{style=&quot;table-layout:auto&quot;}

Si l’une de ces variables n’est pas cohérente pour chaque type d’implémentation, Adobe les considère comme des visiteurs distincts. Si le suivi des visiteurs n’est pas effectué de manière transparente sur les types d’implémentation de votre site, la raison la plus courante est que le service d’ID est mal configuré. Voir [Méthodes de mise en oeuvre](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) dans le guide d’utilisation du service d’ID pour plus d’informations.
