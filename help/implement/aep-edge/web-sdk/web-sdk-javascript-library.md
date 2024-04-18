---
title: Envoi de données à Adobe Analytics à l’aide de la bibliothèque JavaScript du SDK Web
description: Commencez par une mise en oeuvre propre du SDK Web pour envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: 316ca1074de36db0d7c9545691e7c6d72a2ed2c4
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 18%

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

>[!IMPORTANT]
>
>Cette méthode de mise en oeuvre nécessite l’utilisation d’un schéma configuré pour Adobe Analytics. Si votre entreprise prévoit d’utiliser votre propre schéma avec Customer Journey Analytics à l’avenir, l’utilisation du schéma Adobe Analytics peut créer une confusion pour les administrateurs ou les architectes de données. Plusieurs options permettent d’atténuer cet obstacle :
>
>* Vous pouvez utiliser le schéma Adobe Analytics dans CJA. Notez que CJA n’a pas de concept de props ou eVars ; ils sont traités comme tout autre champ de schéma. Notez également que l’utilisation du schéma Adobe Analytics dans CJA peut rendre plus difficile l’utilisation d’autres services de plateforme, tels que Adobe Journey Optimizer ou Real-time Customer Data Platform.
>* Vous pouvez utiliser l’objet de données, comme un workflow de migration. Notez que l’utilisation de l’objet de données nécessite que vous mappez chaque champ d’objet de données à un champ de schéma XDM.
>* Vous pouvez ignorer entièrement l’implémentation d’Adobe Analytics et envoyer des données à Adobe Experience Platform à l’aide de votre propre schéma. Cette approche est idéale à long terme et permet à votre entreprise de commencer à utiliser Customer Journey Analytics.

## Procédure de mise en oeuvre de la bibliothèque JavaScript du SDK Web

Présentation générale des tâches d’implémentation :

![Comment mettre en oeuvre Adobe Analytics à l’aide du workflow SDK Web, comme décrit dans cette section.](../../assets/websdk-annotated.png)

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
<td> 4</td>
<td><b>Installez la version autonome prédéfinie</b>. Vous pouvez référencer la bibliothèque (<code>alloy.js</code>) sur le réseau CDN directement sur votre page ou la télécharger et l’héberger sur votre propre infrastructure. Vous pouvez également utiliser le package NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Installer la version autonome prédéfinie</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">utiliser le package NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<td>6</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports en particulier.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurez le SDK Web</b>. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’identifiant de flux de données (anciennement appelé id de configuration Edge ).<code>edgeConfigId</code>), id de l’organisation (<code>orgId</code>) et d’autres options disponibles. Assurez-vous que la correspondance des variables est correcte. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configuration du SDK Web</a><br/><a href="../xdm-var-mapping.md">Mappage des variables d’objet XDM</a></td>
</tr>

<tr>
<td>8</td>
<td><b>Exécutez les commandes</b> et/ou <b>suivez des événements</b>. Une fois le code de base implémenté sur votre page web, vous pouvez commencer à exécuter des commandes et à suivre des évènements à l’aide du SDK.
</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/sendevent/overview.html">Envoi d’événements</a></td>
</tr>

<tr>
<td>9</td><td><b>Étendez et validez votre implémentation</b> avant de la diffuser en production.</td><td></td> 
</tr>
</table>
