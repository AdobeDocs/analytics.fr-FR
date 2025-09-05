---
title: Prise en main d’Activity Map
description: Commencez à utiliser la superposition et les dimensions Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Prise en main d’Activity Map

Activity Map dans Adobe Analytics comprend quatre éléments principaux :

* **Paramètre de la suite de rapports** : vous devez activer Activity Map dans les paramètres de la suite de rapports. Lorsqu’elle est activée, la suite de rapports crée plusieurs variables réservées pour les dimensions et mesures Activity Map.
* **Implémentation** : collectez les données Activity Map sur votre site web ou votre propriété. La personnalisation de la manière dont les données sont collectées peut améliorer la qualité et l’expérience des rapports.
* **Dimensions et mesures Workspace** : lorsque votre implémentation est correctement configurée, vous pouvez utiliser les dimensions et mesures Activity Map dans Analysis Workspace.
* **Recouvrement** : Adobe propose une extension de navigateur pour afficher les données Activity Map dans le cadre de votre site web.

## Activer le paramètre de la suite de rapports

Les rapports Activity Map doivent être activés pour qu’une suite de rapports puisse commencer à collecter des données. Si votre mise en œuvre envoie des données Activity Map à une suite de rapports sans activer la création de rapports Activity Map, les données Activity Map ne sont pas incluses dans l’accès.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Rapports Activity Map]** > **[!UICONTROL Activer les rapports Activity Map]**

L’activation des rapports Activity Map crée plusieurs variables réservées du serveur principal. Voir [Rapports Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) dans le guide d’administration d’Adobe Analytics pour plus d’informations.

## Installation du code

Votre mise en œuvre doit être correctement configurée pour envoyer des données Activity Map à Adobe.

+++Extension de balises du SDK Web

La collecte de données Activity Map nécessite l’extension **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 ou une version ultérieure. Les versions d’extension jusqu’à la version v2.16 ont une prise en charge limitée. Ces versions d’extension précédentes envoient les données d’Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

Le paramètre de configuration **[!UICONTROL Collecte de données Click]** gère la collecte de données Activity Map et est généralement activé par défaut. Vous pouvez vérifier qu’elle est activée dans les paramètres de configuration de l’extension :

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com)
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL Adobe Experience Platform Web SDK]** dans la liste des extensions installées, puis sélectionnez **[!UICONTROL Configurer]** à droite.
1. Recherchez la section intitulée [!UICONTROL Collecte de données] et assurez-vous que la case **[!UICONTROL Activer la collecte de données de clics]** est activée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, apportez vos modifications à une bibliothèque et publiez-les en production.

Voir [Configurer l’extension de balise Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) pour plus d’informations.

+++

+++Bibliothèque JavaScript Web SDK (`alloy.js`)

La collecte de données Activity Map nécessite la bibliothèque JavaScript Web SDK v2.20 ou une version ultérieure. Les versions de bibliothèque jusqu’à la version v2.15 ont une prise en charge limitée. Ces versions de bibliothèque précédentes envoient les données d’Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

La variable de configuration Web SDK [`clickCollectionEnabled`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) gère la collecte automatique des données Activity Map. Elle est activée par défaut, sauf si elle est explicitement désactivée.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extension de balises Adobe Analytics

Le paramètre de configuration **[!UICONTROL Utiliser Activity Map]** gère la collecte de données Activity Map et est généralement activé par défaut. Il est disponible pour toutes les extensions de balise version 1.9.0 ou ultérieure. Vous pouvez vérifier qu’elle est activée dans les paramètres de configuration de l’extension :

1. Connectez-vous à [experience.adobe.com](https://experience.adobe.com)
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste des extensions installées, puis sélectionnez **[!UICONTROL Configurer]** à droite.
1. Assurez-vous que la case **[!UICONTROL Utiliser Activity Map]** est cochée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, apportez vos modifications à une bibliothèque et publiez-les en production.

Voir la présentation de l’extension Adobe Analytics [&#128279;](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/analytics/overview) pour plus d’informations.

+++

+++Bibliothèque JavaScript Adobe Analytics (`AppMeasurement.js`)

Le module Activity Map gère la collecte de données Activity Map et est inclus dans toutes les bibliothèques AppMeasurement version 1.6 ou ultérieure. Vous pouvez examiner le fichier `AppMeasurement.js` pour vous assurer qu’il est bien inclus.

1. Accédez à la [dernière version d’Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) sur GitHub.
1. Téléchargez le fichier compressé de la bibliothèque AppMeasurement, puis ouvrez les `AppMeasurement.js` qu’il contient.
1. Le module Activity Map est inclus près de la partie supérieure de ce fichier. Assurez-vous que ce module est inclus dans la bibliothèque AppMeasurement utilisée par votre site.

+++

## Dimensions disponibles

Lorsqu’Activity Map est activé pour votre suite de rapports et votre implémentation , vous pouvez commencer à utiliser les dimensions suivantes dans Analysis Workspace :

* [[!UICONTROL Lien Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Région Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Page Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Lien Activity Map Par Région]](/help/components/dimensions/activity-map-link-by-region.md)

## Télécharger et installer l’extension de navigateur ou le module complémentaire

Outre les dimensions disponibles dans Analysis Workspace, vous pouvez également afficher les données Activity Map sous forme de superposition sur votre site web. Pour afficher ce recouvrement, téléchargez et installez l’extension de navigateur ou le module complémentaire Activity Map.

**[!UICONTROL Outils]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Télécharger Activity Map]**

Ce lien vous mène à l’extension prise en charge par votre navigateur ou à la marketplace du module complémentaire où vous pouvez l’installer. Une fois installé, l’extension ou le module complémentaire s’affiche en haut à droite de votre navigateur, où vous pouvez vous connecter et activer le recouvrement.
