---
title: Envoyer des données à Adobe Analytics à l’aide de l’extension de balise Web SDK
description: Commencez par une implémentation propre de la collecte de données Adobe Experience Platform pour envoyer des données à Adobe Analytics à l’aide de XDM et du groupe de champs Adobe Analytics ExperienceEvent.
exl-id: 235b3d68-92dd-4ca4-8889-1e1f2d83f47e
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 16%

---

# Envoyer des données à Adobe Analytics à l’aide de l’extension de balise Web SDK

Ce chemin d’implémentation implique une nouvelle installation de Web SDK à l’aide de balises dans la collecte de données Adobe Experience Platform. D’autres chemins d’implémentation sont abordés sur des pages distinctes :

* [Bibliothèque Web SDK JavaScript](web-sdk-javascript-library.md) : nouvelle installation de Web SDK à l’aide de la bibliothèque Web SDK JavaScript (`alloy.js`). Similaire à l’approche de l’extension de balise Web SDK (cette page), sauf que vous gérez l’implémentation vous-même au lieu d’utiliser l’interface utilisateur des balises. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.
* [Extension Analytics vers l’extension Web SDK](analytics-extension-to-web-sdk.md) : adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise Web SDK. Cette approche supprime la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez l’objet `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [Bibliothèque JavaScript AppMeasurement vers Web SDK &#x200B;](appmeasurement-to-web-sdk.md) : approche fluide et méthodique de la migration vers Web SDK, sauf qu’elle n’utilise pas de balises. Au lieu de cela, vous supprimez manuellement la bibliothèque de collecte de données Adobe Analytics (`AppMeasurement.js`) et la remplacez par la bibliothèque JavaScript Web SDK (`alloy.js`).

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de l’extension Web SDK pour envoyer des données à Adobe Analytics présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Approche la plus directe** : ce chemin d’implémentation est le plus simple et est généralement recommandé pour les nouvelles implémentations de Web SDK. Si vous ne devez pas vous soucier d’une implémentation d’Adobe Analytics en cours, renseignez les champs XDM de Web SDK applicables.</li><li>**Schéma prédéfini** : si votre organisation n’a pas besoin de votre propre schéma, vous pouvez simplement utiliser celui destiné à Adobe Analytics. Ce concept s’applique même lorsque vous passez à Customer Journey Analytics ; le concept des props et des eVars ne s’applique pas à Customer Journey Analytics, mais vous pouvez continuer à utiliser les props et les eVars comme de simples dimensions personnalisées.</li><li>**Gestion des balises sans intervention des développeurs** : les balises vous permettent de gérer votre implémentation sans demander aux développeurs d’apporter des modifications de code à votre implémentation. Vos développeurs installent le script du chargeur de balises et vous avez un contrôle total sur la manière dont les données sont collectées.</li></ul> | <ul><li>**Verrouillé dans à l’aide d’un schéma spécifique** : lorsque votre organisation passe à Customer Journey Analytics, vous devez choisir de continuer à utiliser le schéma Adobe Analytics ou de migrer vers le schéma de votre propre organisation (qui serait un jeu de données distinct). Si votre entreprise souhaite éviter à la fois le schéma Adobe Analytics et la migration vers un jeu de données distinct lors du déplacement vers Customer Journey Analytics, Adobe recommande l’une des deux méthodes suivantes :<ul><li>Utilisez l’objet `data` : l’objet `data` permet d’envoyer des données à Adobe Analytics sans se conformer à un schéma XDM. Une fois le schéma de votre organisation créé, vous pouvez utiliser le mappage de flux de données pour mapper `data` champs d’objet à XDM. L’extension [Analytics vers l’extension Web SDK](analytics-extension-to-web-sdk.md) et la bibliothèque JavaScript [AppMeasurement vers Web SDK](appmeasurement-to-web-sdk.md) utilisent toutes deux cet objet `data`.</li><li>Ignorer entièrement Adobe Analytics : si vous implémentez le SDK Web, vous pouvez envoyer ces données à un jeu de données dans Adobe Experience Platform pour les utiliser dans Customer Journey Analytics. Vous pouvez utiliser le schéma de votre choix ; Adobe Analytics n’est pas du tout impliqué dans ce workflow et ne nécessite donc pas le groupe de champs Adobe Analytics ExperienceEvent. Cette méthode entraîne le minimum de dette technique, mais exclut également entièrement Adobe Analytics.</li></ul></ul> |

>[!IMPORTANT]
>
>Cette méthode de mise en œuvre nécessite l’utilisation d’un schéma configuré pour Adobe Analytics. Si votre organisation prévoit d’utiliser votre propre schéma avec Customer Journey Analytics à l’avenir, l’utilisation du schéma Adobe Analytics peut prêter à confusion pour les administrateurs de données ou les architectes. Plusieurs options permettent d’atténuer cet obstacle :
>
>* Vous pouvez utiliser le schéma Adobe Analytics dans CJA. Notez que CJA ne comporte pas de concept de props ou d’eVars ; ils sont traités comme tout autre champ de schéma. Notez également que l’utilisation du schéma Adobe Analytics dans CJA peut rendre plus difficile l’utilisation d’autres services de Platform, tels que Adobe Journey Optimizer ou Real-Time Customer Data Platform.
>* Vous pouvez utiliser l’objet de données, comme pour un processus de migration. Notez que l’utilisation de l’objet de données nécessite de mapper chaque champ d’objet de données à un champ de schéma XDM.
>* Vous pouvez entièrement ignorer l’implémentation d’Adobe Analytics et envoyer des données à Adobe Experience Platform à l’aide de votre propre schéma. Cette approche est idéale à long terme et permet à votre entreprise de commencer à utiliser Customer Journey Analytics.

## Étapes requises pour implémenter l’extension de balise Web SDK

Présentation générale des tâches d’implémentation :

![Comment mettre en œuvre Adobe Analytics à l’aide du workflow d’extension Web SDK, comme décrit dans cette section.](../../assets/websdk-extension-annotated.png)

<table style="width:100%">

<tr>
<th style="width:5%"></th><th style="width:60%"><b>Tâche</b></th><th style="width:35%"><b>Informations supplémentaires</b></th>
</tr>

<tr>
<td>1</td>
<td>Vérifiez que vous avez <b>défini une suite de rapports</b>.</td>
<td><a href="/help/admin/tools/manage-rs/report-suites-admin.md">Gestionnaire de suites de rapports</a></td>
</tr>

<tr>
<td>2</td>
<td><b>Configurer des schémas</b>. Pour normaliser la collecte de données à utiliser dans les applications qui utilisent Adobe Experience Platform, Adobe a créé la norme ouverte et accessible au public, Modèle de données d’expérience (XDM).</td>
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
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports spécifique(s).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>6</td>
<td><b>Créer une propriété de balise</b>. Les propriétés sont des conteneurs globaux utilisés pour référencer les données de la gestion des balises.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/admin/companies-and-properties.html?lang=fr#for-web">Créer ou configurer une propriété de balise pour le web</a></td>
</tr>

<tr>
<td>7</td> 
<td><b>Installez et configurez l’extension SDK web</b> dans la propriété de balise. Configurez l’extension SDK web pour envoyer des données au flux de données configuré à l’étape 4.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/sdk/overview.html?lang=fr">Présentation de l’extension SDK Web d’Adobe Experience Platform</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Itérez, validez et publiez</b> en production. Code incorporé permettant d’inclure la propriété de balise dans les pages de votre site web. Utilisez ensuite des éléments de données, des règles, etc., pour personnaliser votre implémentation.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?lang=fr#embed-code">Code incorporé</a><br/><a href="https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=fr">Présentation de la publication</a></td>
</tr>

</table>
