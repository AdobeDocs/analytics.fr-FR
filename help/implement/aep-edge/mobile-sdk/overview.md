---
title: Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform
description: Utilisez l’extension SDK Mobile dans la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics.
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 100%

---

# Mettre en œuvre Adobe Analytics à l’aide du SDK Mobile d’Adobe Experience Platform

Le SDK Mobile Adobe Experience Platform permet d’optimiser les solutions et services Experience Cloud d’Adobe dans vos applications mobiles. Il est disponible pour Android, iOS et différents frameworks de développement multiplateformes. La configuration est gérée via la collecte de données Adobe Experience Platform.

Pour envoyer des données à Adobe Experience Edge à l’aide du SDK Mobile :

1. Connectez-vous à [Collecte de données Adobe Experience Platform](https://experience.adobe.com/data-collection).
2. Sélectionnez la propriété de votre choix dans la liste, ou [configurez une propriété mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. Accédez à l’onglet Extensions et installez l’extension [Identity for Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network).
4. Installez le [réseau Adobe Experience Platform Edge](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [Configurez un flux de données](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams), en ajoutant Adobe Analytics en tant que service pointant vers la suite de rapports souhaitée.
6. [Installez le SDK](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) sur votre application mobile.

>[!IMPORTANT]
>
>Une extension Adobe Analytics est également disponible dans la collecte de données Adobe Experience Platform. Si vous installez cette extension, vous ne profitez pas de XDM ou du réseau Edge.
