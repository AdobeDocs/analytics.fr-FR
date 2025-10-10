---
title: Envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript Web SDK
description: Commencez par une implémentation propre de Web SDK pour envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript.
exl-id: 593b63ac-e411-4f88-af7e-78f026269ec0
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 18%

---

# Envoyer des données à Adobe Analytics à l’aide de la bibliothèque JavaScript Web SDK

Ce chemin d’implémentation implique une nouvelle installation de Web SDK à l’aide de la bibliothèque JavaScript Web SDK. D’autres chemins d’implémentation sont abordés sur des pages distinctes :

* [Extension de balise Web SDK](web-sdk-tag-extension.md) : nouvelle installation de Web SDK à l’aide de l’extension de balise Web SDK. Similaire à l’approche de la bibliothèque JavaScript Web SDK (cette page), sauf que vous gérez l’implémentation à l’aide de balises dans la collecte de données Adobe Experience Platform. Le groupe de champs Adobe Analytics ExperienceEvent, qui comprend des variables Analytics standard à inclure dans votre schéma XDM, est nécessaire.
* [Extension Analytics vers l’extension Web SDK](analytics-extension-to-web-sdk.md) : adoptez une approche fluide et méthodique pour passer de l’extension de balise Adobe Analytics à l’extension de balise Web SDK. Cette approche supprime la nécessité d’utiliser XDM jusqu’à ce que votre entreprise soit prête à utiliser les services Adobe Experience Platform, tels que Customer Journey Analytics. Utilisez l’objet `data` au lieu de l’objet `xdm` pour envoyer des données à Adobe.
* [Bibliothèque JavaScript AppMeasurement vers Web SDK &#x200B;](appmeasurement-to-web-sdk.md) : approche fluide et méthodique de la migration vers Web SDK, sauf qu’elle n’utilise pas de balises. Au lieu de cela, vous pouvez supprimer manuellement la bibliothèque de collecte de données Adobe Analytics (`AppMeasurement.js`) et la remplacer par la bibliothèque JavaScript Web SDK (`alloy.js`).

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de la bibliothèque JavaScript Web SDK pour envoyer des données à Adobe Analytics présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Approche directe** : ce chemin d’implémentation est plus simple que les approches qui déplacent les implémentations Adobe Analytics existantes. Si vous ne devez pas vous soucier d’une implémentation d’Adobe Analytics en cours, renseignez les champs XDM de Web SDK applicables.</li><li>**Schéma prédéfini** : si votre organisation n’a pas besoin de votre propre schéma, vous pouvez simplement utiliser celui destiné à Adobe Analytics. Ce concept s’applique même lorsque vous passez à Customer Journey Analytics ; le concept des props et des eVars ne s’applique pas à Customer Journey Analytics, mais vous pouvez continuer à utiliser les props et les eVars comme de simples dimensions personnalisées.</li></ul> | <ul><li>**Les modifications d’implémentation nécessitent l’intervention d’un développeur** : si vous souhaitez apporter des modifications à votre implémentation de Web SDK, vous devez collaborer avec votre équipe de développement pour modifier le code sur votre site. L’approche qui utilise l’extension de balise [Web SDK](web-sdk-tag-extension.md) évite cet inconvénient.</li><li>**Verrouillé dans à l’aide d’un schéma spécifique** : lorsque votre organisation passe à Customer Journey Analytics, vous devez choisir de continuer à utiliser le schéma Adobe Analytics ou de migrer vers le schéma de votre propre organisation (qui serait un jeu de données distinct). Si votre entreprise souhaite éviter à la fois le schéma Adobe Analytics et la migration vers un jeu de données distinct lors du déplacement vers Customer Journey Analytics, Adobe recommande l’une des deux méthodes suivantes :</li><ul><li>Utilisez l’objet `data` : l’objet `data` permet d’envoyer des données à Adobe Analytics sans se conformer à un schéma XDM. Une fois le schéma de votre organisation créé, vous pouvez utiliser le mappage de flux de données pour mapper `data` champs d’objet à XDM. L’extension [Analytics vers l’extension Web SDK](analytics-extension-to-web-sdk.md) et la bibliothèque JavaScript [AppMeasurement vers Web SDK](appmeasurement-to-web-sdk.md) utilisent toutes deux cet objet `data`.</li><li>Ignorer entièrement Adobe Analytics : si vous implémentez le SDK Web, vous pouvez envoyer ces données à un jeu de données dans Adobe Experience Platform pour les utiliser dans Customer Journey Analytics. Vous pouvez utiliser le schéma de votre choix ; Adobe Analytics n’est pas du tout impliqué dans ce workflow et ne nécessite donc pas le groupe de champs Adobe Analytics ExperienceEvent. Cette méthode entraîne le minimum de dette technique, mais exclut également entièrement Adobe Analytics.</li></ul></ul> |

>[!IMPORTANT]
>
>Cette méthode de mise en œuvre nécessite l’utilisation d’un schéma configuré pour Adobe Analytics. Si votre organisation prévoit d’utiliser votre propre schéma avec Customer Journey Analytics à l’avenir, l’utilisation du schéma Adobe Analytics peut prêter à confusion pour les administrateurs de données ou les architectes. Plusieurs options permettent d’atténuer cet obstacle :
>
>* Vous pouvez utiliser le schéma Adobe Analytics dans CJA. Notez que CJA ne comporte pas de concept de props ou d’eVars ; ils sont traités comme tout autre champ de schéma. Notez également que l’utilisation du schéma Adobe Analytics dans CJA peut rendre plus difficile l’utilisation d’autres services de Platform, tels que Adobe Journey Optimizer ou Real-Time Customer Data Platform.
>* Vous pouvez utiliser l’objet de données, comme pour un processus de migration. Notez que l’utilisation de l’objet de données nécessite de mapper chaque champ d’objet de données à un champ de schéma XDM.
>* Vous pouvez entièrement ignorer l’implémentation d’Adobe Analytics et envoyer des données à Adobe Experience Platform à l’aide de votre propre schéma. Cette approche est idéale à long terme et permet à votre entreprise de commencer à utiliser Customer Journey Analytics.

## Procédure d’implémentation de la bibliothèque JavaScript Web SDK

Présentation générale des tâches d’implémentation :

![Comment mettre en œuvre Adobe Analytics à l’aide du workflow Web SDK, comme décrit dans cette section.](../../assets/websdk-annotated.png)

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
<td> 4</td>
<td><b>Installez la version autonome prédéfinie</b>. Vous pouvez référencer la bibliothèque (<code>alloy.js</code>) sur le CDN directement sur votre page ou la télécharger et l’héberger sur votre propre infrastructure. Vous pouvez également utiliser le package NPM.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/library.html">Installer la version autonome prédéfinie</a> et <a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/install/npm.html">utiliser le package NPM</a></td>
</tr>

<tr>
<td>5</td>
<td><b>Configurez un flux de données</b>. Un flux de données représente la configuration côté serveur lors de l’implémentation du SDK Web Adobe Experience Platform.</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr">Configurer un flux de données<a></td> 
</tr>

<td>6</td>
<td><b>Ajoutez un service Adobe Analytics</b> à votre flux de données. Ce service contrôle si et comment les données sont envoyées à Adobe Analytics et à quelle(s) suite(s) de rapports spécifique(s).</td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html#analytics">Ajoutez un service Adobe Analytics à un flux de données.</a></td>
</tr>

<tr>
<td>7</td>
<td><b>Configurez le SDK Web</b>. Assurez-vous que la bibliothèque que vous avez installée à l’étape 4 est correctement configurée avec l’identifiant du flux de données (anciennement appelé identifiant de configuration Edge (<code>datastreamId</code>)), l’identifiant de l’organisation (<code>orgId</code>) et les autres options disponibles. Assurez-vous que le mappage des variables est correct. </td>
<td><a href="https://experienceleague.adobe.com/docs/experience-platform/web-sdk/commands/configure/overview.html">Configurer le mappage des variables d’objet Web SDK</a><br/><a href="../xdm-var-mapping.md">XDM</a></td>
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
