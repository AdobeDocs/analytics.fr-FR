---
title: Résolution des problèmes liés à la collecte de données Activity Map
description: Déterminer pourquoi vous ne pouvez pas voir les données Activity Map dans les demandes d’image
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
TQID: https://experienceleague.adobe.com/gv0QMe3b8xe17THNCvDN0g7bPy73XdakcSsZYio8K5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 429
ht-degree: 16%

---

# Résolution des problèmes liés à la collecte de données Activity Map

Si vous ne voyez pas de données pour les dimensions Activity Map, utilisez cette page pour en déterminer la raison.

## Confirmer la collecte de données à l’aide du débogueur

Tout d’abord, assurez-vous qu’AppMeasurement collecte correctement les données Activity Map.

1. Téléchargez et installez l’[extension Adobe CX Enterprise Debugger Chrome](https://experienceleague.adobe.com/fr/docs/experience-platform/debugger/home).
2. Accédez à votre page web, puis cliquez sur un lien.
3. Lors du chargement de la page suivante, ouvrez le débogueur. Vérifiez que vous voyez les variables de données contextuelles Activity Map prises en sandwich entre `activitymap.` et `.activitymap` :

## Raisons possibles de l’absence de données Activity Map

Vérifiez chacun des éléments suivants pour vous assurer que les composants Activity Map sont présents :

* **Version d’AppMeasurement** : Activity Map est pris en charge sur les versions 1.6 et ultérieures. De nombreux problèmes de cas Edge sont résolus lorsque vous effectuez une mise à niveau vers la dernière version stable d’AppMeasurement.
* **Module Activity Map** : vérifiez si le module `AppMeasurement_Module_Activity_Map` est présent dans votre fichier `AppMeasurement.js`. Si votre implémentation utilise Adobe Experience Platform pour collecter des données, assurez-vous que la case **[!UICONTROL Activer ClickMap]** est cochée lors de la configuration de l’extension Analytics sous **[!UICONTROL Suivi des liens]**.
* **Le cookie `s_sq`** : Activity Map dépend du cookie `s_sq` pour la collecte des données.
   * Assurez-vous que la variable `cookieDomainPeriods` est correctement définie, en particulier pour les domaines régionaux tels que `*.co.uk` ou `*.co.jp`.
   * Assurez-vous que la variable `linkInternalFilters` est définie sur les valeurs souhaitées. Si un lien cliqué ne correspond pas aux filtres internes, Activity Map le considère comme un lien de sortie et ne collecte pas de données.
* **incrustation Activity Map en cours d’exécution** : AppMeasurement ne suit pas les données de clic pour votre page web lorsque la superposition Activity Map est activée.

Affiche les paramètres de navigateur qui ne sont pas compatibles avec l’utilisation d’Activity Map. Adobe recommande de désactiver ces paramètres.

## Chrome

![](assets/Chrome1.png)

![](assets/Chrome2.png)

![](assets/Chrome3.png)

## Firefox

![](assets/Firefox.png)

## Safari

![](assets/Safari1.png)

![](assets/Safari2.png)

## Internet Explorer

![](assets/IE1.png)


**Validation**

Interagissez avec les appels à l’aide de l’onglet Réseau de Developer Console :

1. Chargez le script de développement Launch sur le site.
1. En cas de clic sur les éléments, recherchez « /ee » dans l’onglet Réseau.

Adobe Experience Platform Debugger :

1. Téléchargez et installez l’[Adobe Experience Platform Debugger](https://chromewebstore.google.com/detail/adobe-experience-platform/bfnnokhpnncpkdmbokanobigaccjkpob).
1. Accédez à [!UICONTROL Journaux] > [!UICONTROL Edge] > [!UICONTROL Connexion à Edge].

* **L’appel d’interaction ne se déclenche pas dans l’onglet Réseau** : la collecte de données de clics dans un appel de collecte, filtrez avec `"/ee"` ou `"collect?"`.
* **Il n’existe aucun affichage de payload pour l’appel de collecte** : l’appel de collecte est conçu de telle sorte que le suivi n’affecte pas la navigation vers d’autres sites. Par conséquent, la fonction de déchargement de document est applicable aux appels de collecte. Cette fonctionnalité n’a aucun impact sur votre collecte de données, mais si vous devez valider sur la page, ajoutez des `target="_blank"` à l’élément correspondant. Le lien s’ouvre dans un nouvel onglet.
