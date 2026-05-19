---
title: Prise en main d’Activity Map
description: Commencez à utiliser le recouvrement et les dimensions Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
TQID: https://experienceleague.adobe.com/Wt30b3LTZWyzAQFOKqkqBdWH2Ifatq5FLp-Z0z7nktA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: af860ea2bf90f0f25bfb95b943d9ae11bf808028
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 97%

---

# Prise en main d’Activity Map

Activity Map dans Adobe Analytics comprend quatre éléments principaux :

* **Paramètre de la suite de rapports** : vous devez activer Activity Map dans les paramètres de la suite de rapports. Lorsqu’elle est activée, la suite de rapports crée plusieurs variables réservées pour les dimensions et mesures Activity Map.
* **Implémentation** : collectez les données Activity Map sur votre site web ou votre propriété. La personnalisation de la manière dont les données sont collectées peut améliorer la qualité et l’expérience des rapports.
* **Dimensions et mesures Workspace** : lorsque votre implémentation est correctement configurée, vous pouvez utiliser les dimensions et mesures Activity Map dans Analysis Workspace.
* **Recouvrement** : Adobe propose une extension de navigateur pour afficher les données Activity Map dans le cadre de votre site web. Cette fonctionnalité n’est pas disponible pour les implémentations du SDK web.

## Activer le paramètre de suite de rapports

Les rapports Activity Map doivent être activés pour qu’une suite de rapports puisse commencer à collecter des données. Si votre mise en œuvre envoie des données Activity Map à une suite de rapports sans activer la création de rapports Activity Map, les données correspondantes ne sont pas incluses dans l’accès.

**[!UICONTROL Admin]** > **[!UICONTROL Suites de rapports]** > Sélectionner une suite de rapports > **[!UICONTROL Modifier les paramètres]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Rapports Activity Map]** > **[!UICONTROL Activer les rapports Activity Map]**

L’activation des rapports Activity Map crée plusieurs variables réservées back-end. Pour plus d’informations, consultez [Rapports Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) dans le guide d’administration Adobe Analytics.

## Installation du code

Votre mise en œuvre doit être correctement configurée pour envoyer des données Activity Map à Adobe. L’extension de navigateur de recouvrement n’est pas disponible lorsqu’Adobe Analytics est implémenté avec le SDK web.

+++Extension de balises du SDK Web

La collecte de données Activity Map nécessite l’extension **[!UICONTROL Adobe Experience Platform SDK web]** v2.23 ou une version ultérieure. Les versions d’extension jusqu’à la version v2.16 ont une prise en charge limitée. Ces versions d’extension précédentes envoient les données d’Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

Le paramètre de configuration **[!UICONTROL Collecte de données de clics]** gère la collecte de données Activity Map et est généralement activé par défaut. Vous pouvez vérifier qu’il est activé dans les paramètres de configuration de l’extension :

1. Connectez-vous à [Adobe CX Enterprise](https://experience.adobe.com) à l’aide de vos informations d’identification Adobe ID.
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL Adobe Experience Platform SDK web]** dans la liste des extensions installées, puis sélectionnez **[!UICONTROL Configurer]** à droite.
1. Recherchez la section intitulée [!UICONTROL Collecte de données] et assurez-vous que la case **[!UICONTROL Activer la collecte de données de clics]** est activée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, apportez vos modifications à une bibliothèque et publiez-les en production.

Consultez [Configurer l’extension de balise SDK web](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) pour plus d’informations.

+++

+++Bibliothèque JavaScript du SDK web (`alloy.js`)

La collecte de données Activity Map nécessite la bibliothèque JavaScript du SDK web v2.20 ou une version ultérieure. Les versions de bibliothèque jusqu’à la version v2.15 ont une prise en charge limitée. Ces versions de bibliothèque précédentes envoient les données d’Activity Map dans un événement distinct du reste de vos données. Cet événement supplémentaire augmente le nombre d’accès que vous envoyez à Adobe Analytics ou Adobe Experience Platform.

La variable de configuration du SDK web [`clickCollectionEnabled`](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) gère la collecte automatique des données Activity Map. Elle est activée par défaut, sauf si elle est explicitement désactivée.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extension de balise Adobe Analytics

Le paramètre de configuration **[!UICONTROL Utiliser Activity Map]** gère la collecte de données Activity Map et est généralement activé par défaut. Cette option est disponible pour toutes les extensions de balise version 1.9.0 ou ultérieure. Vous pouvez vérifier qu’il est activé dans les paramètres de configuration de l’extension :

1. Connectez-vous à [Adobe CX Enterprise](https://experience.adobe.com) à l’aide de vos informations d’identification Adobe ID.
1. Sélectionnez **[!UICONTROL Collecte de données]** dans le menu d’accès rapide ou le sélecteur de produits en haut à droite.
1. Sélectionnez **[!UICONTROL Balises]** dans le menu de navigation de gauche.
1. Sélectionnez la balise à modifier.
1. Sélectionnez **[!UICONTROL Extensions]** dans le menu de navigation de gauche.
1. Sélectionnez **[!UICONTROL Adobe Analytics]** dans la liste des extensions installées, puis sélectionnez **[!UICONTROL Configurer]** à droite.
1. Assurez-vous que la case **[!UICONTROL Utiliser Activity Map]** est cochée.
1. Sélectionnez **[!UICONTROL Enregistrer]**.
1. Si nécessaire, apportez vos modifications à une bibliothèque et publiez-les en production.

Pour plus d’informations, consultez [Vue d’ensemble de l’extension Adobe Analytics](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/analytics/overview).

+++

+++Bibliothèque JavaScript Adobe Analytics (`AppMeasurement.js`)

Le module Activity Map gère la collecte de données Activity Map et est inclus dans toutes les bibliothèques AppMeasurement version 1.6 ou ultérieure. Vous pouvez examiner le fichier `AppMeasurement.js` pour vous assurer qu’il est bien inclus.

1. Accédez à la [dernière version d’Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) sur GitHub.
1. Téléchargez le fichier compressé de la bibliothèque AppMeasurement, puis ouvrez `AppMeasurement.js` à l’intérieur.
1. Le module Activity Map est inclus près de la partie supérieure de ce fichier. Assurez-vous que ce module est inclus dans la bibliothèque AppMeasurement utilisée par votre site.

+++

## Dimensions disponibles

Lorsqu’Activity Map est activé pour votre suite de rapports et votre implémentation, vous pouvez commencer à utiliser les dimensions suivantes dans Analysis Workspace :

* [[!UICONTROL Lien d’Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Région d’Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Page d’Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Lien d’Activity Map par région]](/help/components/dimensions/activity-map-link-by-region.md)

## Télécharger et installer l’extension de navigateur ou le module complémentaire

Outre les dimensions disponibles dans Analysis Workspace, vous pouvez également afficher les données Activity Map sous forme de recouvrement sur votre site web. Pour afficher ce recouvrement, téléchargez et installez l’extension de navigateur ou le module complémentaire Activity Map.

**[!UICONTROL Outils]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Télécharger Activity Map]**

Ce lien vous mène à l’extension prise en charge par votre navigateur ou à la marketplace du module complémentaire où vous pouvez l’installer. Une fois l’installation effectuée, l’extension ou le module complémentaire s’affiche en haut à droite de votre navigateur, où vous pouvez vous connecter et activer le recouvrement.
