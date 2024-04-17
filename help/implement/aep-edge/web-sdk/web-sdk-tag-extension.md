---
title: Envoi de données à Adobe Analytics à l’aide de l’extension de balise SDK Web
description: Commencez par une mise en oeuvre propre de la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics à l’aide de XDM et du groupe de champs ExperienceEvent Adobe Analytics.
hide: true
hidefromtoc: true
source-git-commit: d6c16d8841110e3382248f4c9ce3c2f2e32fe454
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 17%

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

>[!CAUTION]
>
>Cette méthode de mise en oeuvre nécessite l’utilisation d’un schéma configuré pour Adobe Analytics. Si votre entreprise prévoit d’utiliser votre propre schéma avec Customer Journey Analytics à l’avenir, l’utilisation du schéma Adobe Analytics peut créer une confusion pour les administrateurs ou les architectes de données. Plusieurs options permettent d’atténuer cet obstacle :
>
>* Vous pouvez utiliser le schéma Adobe Analytics dans CJA. Notez que CJA n’a pas de concept de props ou eVars ; ils sont traités comme tout autre champ de schéma. Notez également que l’utilisation du schéma Adobe Analytics dans CJA peut rendre plus difficile l’utilisation d’autres services de plateforme, tels que Adobe Journey Optimizer ou Real-time Customer Data Platform.
>* Vous pouvez utiliser l’objet de données, comme un workflow de migration. Notez que l’utilisation de l’objet de données nécessite que vous mappez chaque champ d’objet de données à un champ de schéma XDM.
>* Vous pouvez ignorer entièrement l’implémentation d’Adobe Analytics et envoyer des données à Adobe Experience Platform à l’aide de votre propre schéma. Cette approche est idéale à long terme et permet à votre entreprise de commencer à utiliser Customer Journey Analytics.

## Procédure de mise en oeuvre de l’extension de balise SDK Web

Présentation générale des tâches d’implémentation :

![Comment mettre en oeuvre Adobe Analytics à l’aide du workflow d’extension du SDK Web, comme décrit dans cette section.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="/help/admin/admin/c-manage-report-suites/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configuration de schémas</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=fr">Présentation de l’interface utilisateur des schémas</a></td>
</tr>

<tr>
<td>3</td>
<td><b>Créez une couche de données</b> pour gérer le suivi des données sur votre site web.</td>
<td><a href="../../prepare/data-layer.md">Créer une couche de données</a></td>
</tr>

<tr>
<td>4</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<tr>
<td>5</td> 
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports en particulier.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Créez une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html#for-web">Créer ou configurer une propriété de balise pour le web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installez et configurez l’extension SDK web</b> dans la propriété de balise. Configurez l’extension SDK web pour envoyer des données au flux de données configuré à l’étape 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr">Présentation de l’extension SDK Web d’Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itérez, validez et publiez</b> en production. Incorporez le code pour inclure votre propriété de balise aux pages de votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html#embed-code">Code incorporé</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr">Présentation de la publication</a></td>
</tr>

</table>
