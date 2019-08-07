---
description: Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.
keywords: Implémentation d'Analytics ; javascript ; implémentation javascript ; appmeasurement ; télécharger appmeasurement ; Service d'identité ; visitorapi. js ; mise en cache ; compression appmeasurement
seo-description: Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.
seo-title: Présentation de la mise en œuvre JavaScript
solution: Analytics
title: Présentation de la mise en œuvre JavaScript
topic: Développeur et mise en œuvre
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 883eb12c6c0f9b566dd485227d19cee16d9cfadc

---


# Présentation de la mise en œuvre JavaScript

Pour commencer à utiliser Analytics, des données doivent être envoyées à une suite de rapports afin de les afficher dans des rapports.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). Toutefois, dans certains cas, il est possible que vous vouliez mettre en œuvre Analytics à l’aide de l’ancienne méthode JavaScript.

>[!NOTE]
>
>Cette section décrit la méthode héritée d'implémentation d'Analytics. All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## Procédure de mise en œuvre {#section_73961BAD5BB4430A95E073DE5C026277}

Pour implémenter une page avec du code pour collecter des données, vous devez avoir accès aux serveurs d’hébergement afin de télécharger du nouveau contenu sur votre site Web. Disposer d’un site Web sur lequel implémenter du code s’avère également utile.

Les étapes suivantes vous invitent à parcourir une mise en œuvre de base d’Adobe Analytics.

| Tâche | Description |
|--- |--- |
| 1. Téléchargez appmeasurement pour JavaScript et le service d'ID. | Connectez-vous à Analytics via Experience Cloud. Le fichier de téléchargement est disponible dans Analytics &gt; Admin &gt; Gestionnaire de code. Le fichier ZIP à télécharger contient plusieurs fichiers.  AppMeasurement.js et VisitorAPI.js sont les fichiers requis lors de la mise en œuvre d’Analytics. |
| 2. Configuration du service d'identité. (anciennement service d'identification des visiteurs) | Voir [Configuration du service d'identité pour Analytics.](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| Mise à jour `AppMeasurement.js`. | Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. Vous devez, au minimum, mettre à jour les variables suivantes :<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>Voir [Renseigner correctement les variables trackingserver et trackingserversecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) ou contactez le service à la clientèle si vous n'êtes pas sûr de ces valeurs. Si les variables ne sont pas correctement définies, les données ne seront pas collectées par votre mise en œuvre.</br> |
| 3. Hôte `AppMeasurement.js` et `VisitorAPI.js`. | Ces fichiers JavaScript principaux doivent être hébergés sur un serveur Web accessible par toutes les pages de votre site : Vous aurez besoin du chemin d’accès à ces fichiers à l’étape suivante. |
| 4. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. `VisitorAPI.js` doit être inclus avant `AppMeasurement.js`:`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page: `script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</li></ul> |
| 5. Mise à jour et déploiement du code de page. | Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. Vous devez, au minimum, mettre à jour les variables suivantes :<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s. pagename = « INSERT-NAME-HERE » (par exemple s. pagename = document. title)</li></ul> |
| 6. Utilisez le débogueur Experience Cloud pour vérifier que les données sont envoyées. | Install the [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). Une fois cet outil installé, chargez une page dans laquelle vous avez déployé le code de page, puis ouvrez le débogueur. Le débogueur affiche des informations détaillées sur les données de collecte qui ont été envoyées : |

## Mise en cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

Le fichier JavaScript est mis en cache dans le navigateur du visiteur après son chargement initial. En règle générale, il n’est pas téléchargé plus d’une fois par session. Il n’est pas téléchargé sur chaque page, même s’il est utilisé par toutes les pages du site. Sur la plupart des sites Web, les utilisateurs visualisent, en moyenne, plus de quelques pages par session. Dès lors, le transfert de code JavaScript utilisé plusieurs fois dans ce fichier peut générer un nombre moins important de données téléchargées globales.

## Compression JavaScript pour AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Si le poids (taille) des pages du code H (AppMeasurement pour JavaScript 1.0 est précompressé) vous préoccupe, Adobe vous conseille d’envisager la compression du fichier à l’aide de GZIP. GZIP est pris en charge par les principaux navigateurs du marché ; il offre de meilleures performances que la compression JavaScript pour compresser et décompresser le fichier JavaScript principal [!DNL s_code.js].

Les liens ci-dessous vous aident à comprendre l’utilisation de la fonctionnalité GZIP sur votre site en vue de gérer la compression du code JavaScript du fichier [!DNL s_code.js] :

[Module Apache mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html) (en anglais)

[Activation de la compression Gzip avec Tomcat et Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/) (en anglais)
