---
title: Dépannage de la collecte de données de Activity Map
description: Déterminer pourquoi vous ne pouvez pas voir les données de Activity Map dans les demandes d’image
feature: 'Activity Map  '
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# Dépannage de la collecte de données de Activity Map

Si vous ne voyez pas de données pour les dimensions du Activity Map, utilisez cette page pour déterminer pourquoi.

## Confirmation de la collecte des données à l’aide du débogueur

Tout d’abord, assurez-vous qu’AppMeasurement collecte correctement les données du Activity Map.

1. Téléchargez et installez l’[extension Adobe Experience Cloud Debugger pour Chrome ](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=fr).
2. Accédez à votre page web, puis cliquez sur un lien.
3. Au chargement de la page suivante, ouvrez le débogueur. Vérifiez que les variables de données contextuelles du Activity Map s’affichent entre `activitymap.` et `.activitymap` :

![Données du débogueur](assets/debugger.png)

## Raisons possibles de l’absence de données de Activity Map

Vérifiez chacun des éléments suivants pour vous assurer que les composants Activity Map sont présents :

* **Version** d’AppMeasurement : Activity Map est pris en charge sur v1.6 et versions ultérieures. De nombreux problèmes de cas de périphérie sont résolus lorsque vous effectuez une mise à niveau vers la dernière version stable d’AppMeasurement.
* **Module** Activity Map : Vérifiez si le  `AppMeasurement_Module_Activity_Map` module est présent dans votre  `AppMeasurement.js` fichier . Si votre mise en oeuvre utilise Adobe Experience Platform Launch, assurez-vous que l’option **[!UICONTROL Activer le ClickMap]** est cochée lors de la configuration de l’extension Analytics sous **[!UICONTROL Suivi des liens]**.
* **Le  `s_sq` cookie** : Activity Map dépend du  `s_sq` cookie pour la collecte de données.
   * Assurez-vous que la variable `cookieDomainPeriods` est correctement définie, en particulier pour les domaines régionaux tels que `*.co.uk` ou `*.co.jp`.
   * Assurez-vous que la variable `linkInternalFilters` est définie sur les valeurs souhaitées. Si un lien cliqué ne correspond pas aux filtres internes, Activity Map le considère comme un lien de sortie et ne collecte pas de données.
* **Superposition de Activity Map en cours d’exécution** : AppMeasurement n’effectue pas le suivi des données de clics pour votre page web lorsque la superposition du Activity Map est activée.
