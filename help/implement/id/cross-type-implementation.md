---
title: Suivi sur différents types de mises en œuvre
description: Utilisez différents types de mise en œuvre et effectuez un suivi transparent des visiteurs entre eux.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 47%

---

# Suivi sur différents types de mises en œuvre

L’architecture principale d’une implémentation Adobe Analytics est cohérente pour tous les types d’implémentation. Le processus implique de définir des variables et de les compiler dans une demande d’image envoyée aux serveurs de collecte de données d’Adobe. Ce concept signifie que vous pouvez basculer facilement entre AppMeasurement, le SDK Web et leurs extensions respectives dans la collecte de données Adobe Experience Platform sur différentes pages du même site.

Adobe recommande de maintenir une cohérence sur l’ensemble de l’implémentation d’un site en utilisant le même type d’implémentation sur toutes les pages. Cependant, si des parties de votre site ont des exigences différentes, vous pouvez utiliser cette page pour vous assurer que le suivi des visiteurs et visiteuses est cohérent entre les pages.

Si vous utilisez plusieurs types d’implémentation (des demandes d’image codées en dur et AppMeasurement, par exemple), assurez-vous que les variables suivantes sont correctement définies et qu’elles correspondent.

>[!NOTE]
>
>Tous les types d’implémentation doivent utiliser le même type d’identification des visiteurs (Analytics ID hérité, Visitor ID Service ou Experience Platform Identity Service). Adobe recommande d’utiliser un ECID dans toutes les implémentations lorsque cela est possible.

| Variable | Extension de balises du SDK Web | Web SDK (Alloy) | Extension Analytics | AppMeasurement | Demande d’image codée en dur |
|---|---|---|---|---|---|
| Identifiant de suite de rapports | Ajouter Adobe Analytics en tant que service lors de la [Configuration d’un flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure) | Ajouter Adobe Analytics en tant que service lors de la [Configuration d’un flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure) | [!UICONTROL Suites de rapports] sous la section [!UICONTROL Gestion des bibliothèques] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/analytics/overview) | Argument de chaîne en [`s_gi`](../vars/functions/s-gi.md) | Partie de l’URL `pathname` (après `/b/ss/`) |
| Service d’identification des visiteurs | Inclut de manière native le [service Experience Platform Identity](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home) ; nécessite que [`idMigrationEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/idmigrationenabled) lisiez les cookies du service d’identification des visiteurs | Inclut de manière native le [service d’identités ](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/home) ; nécessite [[!UICONTROL Migration de l’ECID de l’API visiteur vers le SDK web]](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity) pour lire les cookies du service d’identification visiteur | Utilisez l’extension de balise [’[!UICONTROL Service Experience Cloud ID]’](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/id-service/overview), qui met en œuvre le service [Visitor ID](https://experienceleague.adobe.com/fr/docs/id-service/using/home) | Mettre en œuvre le [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home) (`VisitorAPI.js`) | Effectuez un [appel distinct au service d’identification des visiteurs](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) pour obtenir l’identifiant souhaité et inclure l’`mid` dans la chaîne de requête |
| domaine Edge | Le champ [!UICONTROL Domaine ] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | La propriété `edgeDomain` lors de la [Configuration du SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL Serveur de suivi SSL] dans la section [!UICONTROL Général] lors de la [Configuration de l’extension](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/analytics/overview) | La variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | Le `hostname` de l’URL de demande d’image |

>[!NOTE]
>
>Les implémentations basées sur AppMeasurement (y compris l’extension de balise Analytics) ne sont pas compatibles avec le [service d’identités Experience Platform](https://experienceleague.adobe.com/fr/docs/id-service/using/home). Vous devez utiliser le plus petit dénominateur commun d’identification des visiteurs pour la synchronisation entre les types d’implémentation, qui est généralement le [service d’identification des visiteurs](https://experienceleague.adobe.com/fr/docs/id-service/using/home) (`VisitorAPI.js`).

Si l’une de ces variables n’est pas cohérente pour chaque type d’implémentation, Adobe les considère probablement comme des visiteurs et visiteuses distincts. Si le suivi des visiteurs n’est pas transparent sur plusieurs types d’implémentation de votre site, la raison la plus courante est que l’identification des visiteurs est configurée de manière incorrecte. Assurez-vous que chaque type d’implémentation obtient correctement le même ECID (`mid` [chaîne de requête](/help/implement/validate/query-parameters.md)) sur l’ensemble de votre site.
