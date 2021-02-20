---
title: Résolution des problèmes de collecte de données des Activity Map
description: Déterminer pourquoi vous ne pouvez pas afficher les données Activity Map dans les demandes d’image
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---


# Résolution des problèmes de collecte de données des Activity Map

Si vous ne voyez pas de données pour les dimensions de Activity Map, utilisez cette page pour déterminer pourquoi.

## Confirmer la collecte de données à l’aide du débogueur

Tout d’abord, assurez-vous qu’AppMeasurement collecte correctement les données du Activity Map.

1. Téléchargez et installez [Adobe Experience Cloud Debugger Chrome Extension](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr-FR).
2. Accédez à votre page Web, puis cliquez sur un lien.
3. Lors du chargement de la page suivante, ouvrez le débogueur. Vérifiez que les variables de données contextuelles Activity Map sont codées entre `activitymap.` et `.activitymap` :

![Données du débogueur](assets/debugger.png)

## Raisons possibles de l&#39;absence de données de Activity Map

Vérifiez chacun des éléments suivants pour vous assurer que les composants Activity Map sont présents :

* **Version** d’AppMeasurement : Le Activity Map est pris en charge sur la version 1.6 et ultérieure. De nombreux problèmes liés aux périphériques sont résolus lorsque vous effectuez la mise à niveau vers la dernière version stable d’AppMeasurement.
* **Module** Activity Map : Vérifiez si le  `AppMeasurement_Module_Activity_Map` module est présent dans votre  `AppMeasurement.js` fichier. Si votre implémentation utilise Adobe Experience Platform Launch, assurez-vous que **[!UICONTROL Activer le ClickMap]** est coché lors de la configuration de l’extension Analytics sous **[!UICONTROL Suivi de liens]**.
* **Le  `s_sq` cookie** : Le Activity Map dépend du  `s_sq` cookie pour la collecte de données.
   * Assurez-vous que la variable `cookieDomainPeriods` est correctement définie, en particulier pour les domaines régionaux tels que `*.co.uk` ou `*.co.jp`.
   * Assurez-vous que la variable `linkInternalFilters` est définie sur les valeurs souhaitées. Si un lien cliqué ne correspond pas aux filtres internes, le Activity Map le considère comme un lien de sortie et ne collecte pas de données.
* **Incrustation Activity Map en cours d’exécution** : AppMeasurement ne suit pas les données de clics pour votre page Web lorsque l’incrustation du Activity Map est activée.
