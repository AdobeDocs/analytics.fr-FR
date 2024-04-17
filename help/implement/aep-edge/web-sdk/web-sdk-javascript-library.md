---
title: Envoi de données à Adobe Analytics à l’aide de la bibliothèque JavaScript du SDK Web
description: Commencez par une mise en oeuvre propre du SDK Web pour envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Envoi de données à Adobe Analytics à l’aide de la bibliothèque JavaScript du SDK Web

Ce chemin d’implémentation implique une nouvelle installation du SDK Web à l’aide de la bibliothèque JavaScript du SDK Web. D’autres chemins de mise en oeuvre sont abordés sur des pages distinctes :

* [Extension de balise SDK Web](web-sdk-tag-extension.md): nouvelle installation du SDK Web à l’aide de l’extension de balise du SDK Web. Similaire à l’approche de la bibliothèque JavaScript du SDK Web (cette page), à la différence que vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Il nécessite que le groupe de champs ExperienceEvent d’Adobe Analytics, qui inclut des variables Analytics standard à inclure dans votre schéma XDM.
* [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md): adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise SDK web. Cette approche élimine la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez la variable `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [AppMeasurement à la bibliothèque JavaScript du SDK Web](appmeasurement-to-web-sdk.md): approche fluide et méthodique de la migration vers le SDK Web, sauf qu’il n’utilise pas de balises. Vous pouvez plutôt supprimer manuellement la bibliothèque de collecte de données Adobe Analytics (`AppMeasurement.js`) et remplacez-le par la bibliothèque JavaScript du SDK Web (`alloy.js`).

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de la bibliothèque JavaScript du SDK Web pour envoyer des données à Adobe Analytics présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Approche directe**: ce chemin d’implémentation est plus simple que les approches qui déplacent les implémentations Adobe Analytics existantes. Si vous ne souhaitez pas vous soucier d’une mise en oeuvre Adobe Analytics actuelle, renseignez les champs XDM du SDK Web applicables.</li><li>**Schéma prédéfini**: si votre entreprise n’a pas besoin de votre propre schéma, vous pouvez simplement utiliser le schéma orienté vers Adobe Analytics. Ce concept s’applique même lorsque vous passez au Customer Journey Analytics ; le concept de props et d’eVars ne s’applique pas à Customer Journey Analytics, mais vous pouvez continuer à utiliser les props et eVars comme dimensions personnalisées simples.</li></ul> | <ul><li>**Les modifications de mise en oeuvre nécessitent une intervention du développeur**: si vous souhaitez apporter des modifications à la mise en oeuvre de votre SDK Web, vous devez travailler avec votre équipe de développement pour modifier le code sur votre site. L’approche qui utilise la variable [Extension de balise SDK Web](web-sdk-tag-extension.md) évite ce désavantage.</li><li>**Connecté à l’aide d’un schéma spécifique**: lorsque votre organisation passe à Customer Journey Analytics, vous devez choisir de continuer à utiliser le schéma Adobe Analytics ou de migrer vers le schéma de votre propre organisation (qui serait un jeu de données distinct). Si votre entreprise souhaite éviter le schéma Adobe Analytics et la migration vers un jeu de données distinct lors du passage à Customer Journey Analytics, Adobe recommande l’une des deux méthodes suivantes :</li><ul><li>Utilisez la variable `data` Objet : `data` vous permet d’envoyer des données à Adobe Analytics sans respecter un schéma XDM. Une fois le schéma de votre organisation créé, vous pouvez utiliser le mappage de flux de données pour mapper. `data` des champs d’objet vers XDM. Les deux [Extension Analytics vers l’extension SDK Web](analytics-extension-to-web-sdk.md) et [AppMeasurement à la bibliothèque JavaScript du SDK Web](appmeasurement-to-web-sdk.md) utilisez ceci `data` .</li><li>Ignorer entièrement Adobe Analytics : si vous mettez en oeuvre le SDK Web, vous pouvez envoyer ces données à un jeu de données dans Adobe Experience Platform en vue de les utiliser dans Customer Journey Analytics. Vous pouvez utiliser n’importe quel schéma de votre choix ; Adobe Analytics n’est pas du tout impliqué dans ce workflow et ne nécessite donc pas le groupe de champs Adobe Analytics ExperienceEvent . Cette méthode engendre le moins de dettes techniques possible, mais elle ne tient pas compte d’Adobe Analytics.</li></ul></ul> |
