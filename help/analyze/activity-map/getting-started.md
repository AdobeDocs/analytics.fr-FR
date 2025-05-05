---
title: Prise en main d’Activity Map
description: Commencez à utiliser la superposition et les dimensions Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Prise en main d’Activity Map

Activity Map dans Adobe Analytics se compose de quatre éléments principaux :

* **Paramètre de suite de rapports** : vous devez activer l’Activity Map dans les paramètres de la suite de rapports. Lorsqu’elle est activée, la suite de rapports crée plusieurs variables réservées aux dimensions et mesures Activity Map.
* **Mise en oeuvre** : collectez des données Activity Map sur votre site web ou propriété. La personnalisation de la manière dont les données sont collectées peut améliorer la qualité et l’expérience des rapports.
* **Dimensions et mesures Workspace** : lorsque votre implémentation est correctement configurée, vous pouvez utiliser les dimensions et mesures Activity Map dans Analysis Workspace.
* **Superposition** : Adobe offre une extension de navigateur pour afficher les données Activity Map dans le contexte de votre site web.

## Activation du paramètre d’une suite de rapports

Les rapports Activity Map doivent être activés pour une suite de rapports avant de pouvoir commencer à collecter des données. Si votre mise en oeuvre envoie des données Activity Map à une suite de rapports sans que les rapports Activity Map soient activés, les données Activity Map ne sont pas incluses dans l’accès.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Création de rapports Activity Map]** > **[!UICONTROL Activer les rapports Activity Map]**

L’activation des rapports Activity Map crée plusieurs variables réservées d’arrière-plan. Pour plus d’informations, voir [Rapports Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) dans le guide d’administration d’Adobe Analytics.

## Installation du code

Votre mise en oeuvre doit être correctement configurée pour envoyer des données Activity Map à Adobe.

+++Extension de balise du SDK Web 

La collecte de données des Activity Map requiert l’extension **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 ou version ultérieure. Les versions d’extension jusqu’à la version 2.16 ont une prise en charge limitée. Ces versions d’extension précédentes envoient des données Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

Le paramètre de configuration **[!UICONTROL Clic sur la collecte de données]** gère la collecte de données Activity Map et est généralement activé par défaut. Vous pouvez vérifier qu’elle est activée dans les paramètres de configuration de l’extension :

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com)
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL SDK Web Adobe Experience Platform]** dans la liste des extensions installées, puis sélectionnez **[!UICONTROL Configurer]** à droite.
1. Recherchez la section intitulée [!UICONTROL Collecte de données] et assurez-vous que la case à cocher **[!UICONTROL Activer la collecte de données de clic]** est activée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, créez vos modifications dans une bibliothèque et publiez-les en production.

Pour plus d’informations, voir [Configuration de l’extension de balise SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) .

+++

+++Bibliothèque JavaScript du SDK Web  (`alloy.js`)

La collecte de données des Activity Map requiert la bibliothèque JavaScript SDK Web version 2.20 ou ultérieure. La prise en charge des versions de bibliothèque jusqu’à la version 2.15 est limitée. Ces versions précédentes de la bibliothèque envoient des données Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

La variable de configuration du SDK Web [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) gère la collecte automatique des données Activity Map. Elle est activée par défaut, sauf si elle est explicitement désactivée.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extension de balise Adobe Analytics

Le paramètre de configuration **[!UICONTROL Utiliser l’Activity Map]** gère la collecte de données Activity Map et est généralement activé par défaut. Il est disponible pour toutes les extensions de balise v1.9.0 ou version ultérieure. Vous pouvez vérifier qu’elle est activée dans les paramètres de configuration de l’extension :

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com)
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste des extensions installées, puis **[!UICONTROL Configurer]** sur la droite.
1. Assurez-vous que la case **[!UICONTROL Utiliser l&#39;Activity Map]** est activée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, créez vos modifications dans une bibliothèque et publiez-les en production.

Pour plus d’informations, consultez la [présentation de l’extension Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) .

+++

+++Bibliothèque JavaScript Adobe Analytics (`AppMeasurement.js`)

Le module Activity Map gère la collecte de données Activity Map et est inclus avec toutes les bibliothèques d’AppMeasurements version 1.6 ou ultérieure. Vous pouvez examiner le fichier `AppMeasurement.js` pour vous assurer qu’il est inclus.

1. Accédez à la [dernière version d’Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) sur GitHub.
1. Téléchargez le fichier de bibliothèque d&#39;AppMeasurements compressé, puis ouvrez le fichier `AppMeasurement.js` contenu à l&#39;intérieur.
1. Le module Activity Map est inclus dans la partie supérieure de ce fichier. Assurez-vous que ce module est inclus dans la bibliothèque AppMeasurement que votre site utilise.

+++

## Dimensions disponibles

Lorsque Activity Map est activé pour votre suite de rapports et votre implémentation, vous pouvez commencer à utiliser les dimensions suivantes dans Analysis Workspace :

* [[!UICONTROL Lien Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Région Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Page Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Lien Activity Map Par Région]](/help/components/dimensions/activity-map-link-by-region.md)

## Téléchargez et installez l’extension ou le module complémentaire du navigateur.

Outre les dimensions disponibles dans Analysis Workspace, vous pouvez également afficher les données Activity Map sous la forme d’une superposition sur votre site web. Pour afficher cette superposition, téléchargez et installez l’extension de navigateur Activity Map ou le module complémentaire.

**[!UICONTROL Outils]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Télécharger l’Activity Map]**

Ce lien vous permet d’accéder à l’extension ou au marché de modules complémentaires pris en charge par votre navigateur où vous pouvez l’installer. Une fois installée, l’extension ou le module complémentaire s’affiche en haut à droite de votre navigateur, où vous pouvez vous connecter et activer la superposition.
