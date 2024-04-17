---
title: Envoi de données à Adobe Analytics à l’aide de l’extension de balise SDK Web
description: Commencez par une mise en oeuvre propre de la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics à l’aide de XDM et du groupe de champs ExperienceEvent Adobe Analytics.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Envoi de données à Adobe Analytics à l’aide de l’extension de balise SDK Web

Ce chemin d’implémentation implique une nouvelle installation du SDK Web à l’aide de balises dans la collecte de données Adobe Experience Platform. D’autres chemins de mise en oeuvre sont abordés sur des pages distinctes :

* [Bibliothèque JavaScript du SDK Web](web-sdk-javascript-library.md): nouvelle installation du SDK Web à l’aide de la bibliothèque JavaScript du SDK Web (`alloy.js`). Similaire à l’approche de l’extension de balise du SDK Web (cette page), à la différence que vous gérez vous-même l’implémentation au lieu d’utiliser l’interface utilisateur des balises. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.
* [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md): adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise SDK web. Cette approche élimine la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez la variable `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [AppMeasurement à la bibliothèque JavaScript du SDK Web](appmeasurement-to-web-sdk.md): approche fluide et méthodique de la migration vers le SDK Web, sauf qu’il n’utilise pas de balises. Vous devez plutôt supprimer manuellement la bibliothèque de collecte de données Adobe Analytics (`AppMeasurement.js`) et remplacez-le par la bibliothèque JavaScript du SDK Web (`alloy.js`).

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de l’extension SDK Web pour envoyer des données à Adobe Analytics présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Approche la plus directe**: ce chemin d’implémentation est le plus simple et généralement le chemin recommandé pour les nouvelles implémentations de SDK Web. Si vous ne souhaitez pas vous soucier d’une mise en oeuvre Adobe Analytics actuelle, renseignez les champs XDM du SDK Web applicables.</li><li>**Schéma prédéfini**: si votre entreprise n’a pas besoin de votre propre schéma, vous pouvez simplement utiliser le schéma orienté vers Adobe Analytics. Ce concept s’applique même lorsque vous passez au Customer Journey Analytics ; le concept de props et d’eVars ne s’applique pas à Customer Journey Analytics, mais vous pouvez continuer à utiliser les props et eVars comme dimensions personnalisées simples.</li><li>**Gestion des balises sans intervention du développeur**: les balises vous permettent de gérer votre mise en oeuvre sans demander aux développeurs d’apporter des modifications au code de votre mise en oeuvre. Les développeurs installent le script de chargeur de balises et vous contrôlez entièrement la manière dont les données sont collectées.</li></ul> | <ul><li>**Connecté à l’aide d’un schéma spécifique**: lorsque votre organisation passe à Customer Journey Analytics, vous devez choisir de continuer à utiliser le schéma Adobe Analytics ou de migrer vers le schéma de votre propre organisation (qui serait un jeu de données distinct). Si votre entreprise souhaite éviter le schéma Adobe Analytics et la migration vers un jeu de données distinct lors du passage à Customer Journey Analytics, Adobe recommande l’une des deux méthodes suivantes :<ul><li>Utilisez la variable `data` Objet : `data` vous permet d’envoyer des données à Adobe Analytics sans respecter un schéma XDM. Une fois le schéma de votre organisation créé, vous pouvez utiliser le mappage de flux de données pour mapper. `data` des champs d’objet vers XDM. Les deux [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md) et [AppMeasurement à la bibliothèque JavaScript du SDK Web](appmeasurement-to-web-sdk.md) utilisez ceci `data` .</li><li>Ignorer entièrement Adobe Analytics : si vous mettez en oeuvre le SDK Web, vous pouvez envoyer ces données à un jeu de données dans Adobe Experience Platform en vue de les utiliser dans Customer Journey Analytics. Vous pouvez utiliser n’importe quel schéma de votre choix ; Adobe Analytics n’est pas du tout impliqué dans ce workflow et ne nécessite donc pas le groupe de champs Adobe Analytics ExperienceEvent . Cette méthode engendre le moins de dettes techniques possible, mais elle ne tient pas compte d’Adobe Analytics.</li></ul></ul> |


